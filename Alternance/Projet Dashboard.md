### **Backend : Api ArgoCD

### **Technologies : 

- Quarkus
- Angular
## **Fonctionnalités

#### *1. Partie Back :
- Se connecter à l'api d'ArgoCD.
- Générer les classes services pour l'api d'ArgoCD.
- Faire appel aux services API.
- Récupérer des informations relatives aux applications.
- Tester ces classes avec des tests et de tests natives.
- Envoyer les objets DTO vers le frontend au bon format.
#### *2. Partie Front :
- Traiter les informations reçues depuis le backend
- Mettre au bon format pour l'affichage
- Afficher les données nécessaires
- Organiser et structurer l'interface
- Filtrer selon les différents critères : métier, nom, version, environnement
## Analyse de l'interface du projet existant :

### 1. Les applications rangées selon les métiers (Logistiques automobile, Transport & Distribution, Lavage & OTC)
- Remarque : Il manque une organisation claire par métiers des application, le rendu des applications ne change pas selon les catégories -> savoir quels applications correspondent aux quels métiers
### 2. "Dashboard Server" un lien vers l'interface du back
- Remarque : Le lien ne se fait pas, on ne peut pas accéder à la page server"
### 3. Fonction de Filtre par critère d'environnement et de nom d'application
- Remarque : utilise certainement des valeurs de noms, et des métadonnées dans l'api. Cependant confus à cause des noms pas très intuitifs
### 4. La liste des application avec le détail sur l'environnement et les différentes versions
- Remarque : les couleurs des éléments de la liste correspondent à l'environnement allant de bleu foncé à blanc (peut être à revoir le choix de couleur). 
- Remarque :  modifier les noms des applications car ces derniers sont pas très intuitifs pour l'utilisateur
- Remarque : pour certaines applications les versions ainsi que l'environnement semblent confondus.

## Analyse approfondie, le code du Backend (gca-kubernetes-api)
- Les dépendances utilisées : openapi; kubernetes client; resteasy-jackson; junit;
- Le DTO contient la version globale, date de version gloable, une map de versions;
- Les classes ressources : Apps; Batch; Core; Environment; Metrics, Version Template
- Le service Version permet de convertir les ressources récupérées depuis le client kubernetes en DTO

## Analyse approfondie, le code du Frontend

