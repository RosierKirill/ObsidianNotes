package com.gcatrans.argocd.resource;  
  
import com.gcatrans.argocd.api.api.ApplicationServiceApi;  
import com.gcatrans.argocd.api.model.V1alpha1Application;  
import com.gcatrans.argocd.dto.ApplicationDTO;  
import jakarta.enterprise.context.ApplicationScoped;  
import jakarta.inject.Inject;  
import jakarta.ws.rs.Consumes;  
import jakarta.ws.rs.GET;  
import jakarta.ws.rs.Path;  
import jakarta.ws.rs.Produces;  
import jakarta.ws.rs.core.MediaType;  
import lombok.RequiredArgsConstructor;  
import org.eclipse.microprofile.rest.client.inject.RestClient;  
  
import java.util.List;  
import java.util.Map;  
import java.util.stream.Collectors;  
  
@Path("/applications")  
@ApplicationScoped  
@RequiredArgsConstructor  
public class ApplicationResource {  
  
    private static final String NOT_FOUND = "NOT FOUND";  
  
    @Inject  
    @RestClient    ApplicationServiceApi applicationServiceApi;  
  
    // Méthode d'application pour transformer un V1alpha1Application en ApplicationDTO  
    // Dépend de l'API ArgoCD ou client Kubernetes    private ApplicationDTO apply(V1alpha1Application application) {  
        ApplicationDTO dto = new ApplicationDTO();  
  
        var metadata = application.getMetadata();  
        var spec = application.getSpec();  
        var operation = application.getOperation();  
  
        String name = metadata.getLabels() != null && metadata.getLabels().containsKey("app.kubernetes.io/name=")  
                ? metadata.getLabels().get("app.kubernetes.io/name=")  
                : NOT_FOUND;  
        String projectName = spec.getProject() != null ? spec.getProject() : NOT_FOUND;  
        String environment = projectName.trim().split("-")[0];  
        String applicationName = metadata.getName() != null ? metadata.getName() : NOT_FOUND;  
        String namespace = spec.getDestination().getNamespace() != null ? spec.getDestination().getNamespace() : NOT_FOUND;  
        Map<String, String> annotations = metadata.getAnnotations() != null ? metadata.getAnnotations() : Map.of();  
  
  
        String ressourceVersion = extraireImageTagDepuisAnnotations(annotations);  
        String cluster = spec.getDestination().getServer() != null  
                ? Map.of(  
                "https://10.10.1.252:6443", "devint-transverse",  
                "https://kubernetes.default.svc", "in-cluster",  
                "https://10.10.2.11:6443", "recppr-lavage",  
                "https://10.10.1.167:6443", "recppr-logauto",  
                "https://10.10.1.206:6443", "recppr-supply",  
                "https://10.10.1.245:6443", "recppr-td"  
        ).getOrDefault(spec.getDestination().getServer(), NOT_FOUND)  
                : NOT_FOUND;  
        String metier = extraireMetierDepuisNom(namespace);  
        String status = application.getStatus() != null && application.getStatus().getHealth() != null  
                ? application.getStatus().getHealth().getStatus()  
                : NOT_FOUND;  
  
        String version = String.join(", ", getImageVersions());  
  
        // dto est rempli avec les valeurs extraites  
        dto.setNamespace(namespace);  
        dto.setProjectName(projectName);  
        dto.setApplicationName(applicationName);  
        dto.setEnvironment(environment);  
        dto.setVersion(version);  
        dto.setMetier(metier);  
        dto.setCluster(cluster);  
        dto.setStatus(status);  
        return dto;  
    }  
  
    private String extraireImageTagDepuisAnnotations(Map<String, String> annotations) {  
        if (annotations == null || annotations.isEmpty()) return "inconnu";  
        return annotations.getOrDefault("argocd-image-updater.argoproj.io/image.allow-tags", "inconnu");  
    }  
  
    private String extraireMetierDepuisNom(String nomProjet) {  
        String[] METIERS = {"td", "logauto", "otc", "lavage", "supply"};  
        for (String metier : METIERS) {  
            if (nomProjet.contains(metier)) {  
                return metier;  
            }  
        }  
        return "inconnu";  
    }  
  
    public List<String> getImageVersions() {  
        // Récupérer la liste des applications  
        var applicationList = applicationServiceApi.applicationServiceList(  
                null, null, null, null, null, null, null, null  
        ).getItems();  
  
        if (applicationList == null) {  
            throw new RuntimeException("La liste des applications est vide.");  
        }  
  
        // Extraire les versions des images à partir des annotations ou des paramètres Helm  
        return applicationList.stream()  
                .map(this::extractImageVersion)  
                .collect(Collectors.toList());  
    }  
  
private String extractImageVersion(V1alpha1Application application) {  
    // Vérifier si les annotations contiennent des informations sur les images  
    Map<String, String> annotations = application.getMetadata() != null ? application.getMetadata().getAnnotations() : null;  
    if (annotations != null && annotations.containsKey("argocd-image-updater.argoproj.io/image.allow-tags")) {  
        return annotations.get("argocd-image-updater.argoproj.io/image.allow-tags");  
    }  
  
    // Vérifier si les paramètres Helm contiennent des informations sur les images  
    if (application.getSpec() != null && application.getSpec().getSource() != null && application.getSpec().getSource().getHelm() != null) {  
        var helmParameters = application.getSpec().getSource().getHelm().getParameters();  
        if (helmParameters != null && !helmParameters.isEmpty()) {  
            return helmParameters.stream()  
                    .filter(param -> param.getName().equalsIgnoreCase("image.tag"))  
                    .map(param -> param.getValue())  
                    .findFirst()  
                    .orElse("Version inconnue");  
        }  
    }  
  
    return "Version inconnue";  
}  
    //Méthodes utilisant l'api ArgoCD  
    // Endpoint pour récupérer la liste des applications    @GET  
    @Produces(MediaType.APPLICATION_JSON)  
    @Consumes(MediaType.APPLICATION_JSON)  
    public List<ApplicationDTO> getApplications() {  
        var applicationList = applicationServiceApi.applicationServiceList(  
                null, null, null, null, null, null, null, null  
        ).getItems();  
  
        if (applicationList == null) {  
            throw new RuntimeException("Application list is null");  
        }  
  
        return applicationList.stream().map(this::apply).collect(Collectors.toList());  
    }  
}  
