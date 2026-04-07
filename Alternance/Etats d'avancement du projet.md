*Premièrement, pour résumé ce qui a été fait :

**Avant le 7/05 analyse en détail du projet initial du Dashboard puis identifications des problèmes, expression de besoin.

- création du nouveau projet du backend, en ajoutant les dépendances nécessaires -> gca-argocd-api
- implémentation de "open api generator" pour générer le client Http pour faire la connexion avec l'api
- étude du fichier spécification .json de l'api argocd
- création de classes de ressources et récupération des Endpoint pour les applications
- création de service ainsi qu'un dto pour les applications
- configuration de l'application via les fichiers gradle.build, et application.properties (authorization, token) *avec de l'aide de David*
- création du service mock de la classe, avec Wiremock
- création des pipeline CI et Tag *avec l'aide de Loic et Stéphanie*
- configuration des taches du pipeline CI
- création des classes test et premiers essais

**Entre mai et juin :

Front : création du projet Front end en Angular avec les fonctionnalités suivantes : 
- filtre par application et environnement
Back : modification du Back end
- modifiaction du DTO 
- ajout de client kubernetes pour recuperer les version
#### Temps consacré environ 1 mois (depuis le retour des vacances le 7 avril)

l'identification des problèmes actuels et le temps nécessaire pour leur résolution :

- Valider les test, et les test natives de Azure (ça serait bien vers la fin de la semaine ~3jours)
- lancer la pipeline CI d'Azure (si le premier est résolu, c'est assez rapide)
- créer un tag
- créer l'image avec la pipeline Tag (pour les deux derniers je l'ai jamais fait donc difficile à estimer ~1 semaine)
- puis continuer avec l'intégration et le déploiement complet de cette partie de l'appli. (2 semaine en idéal si je bloque pas)

En conclusion, j'aurais souhaité terminer en 2 semaines mais c'est très dur d'estimer étant donné que je bloque assez souvent sur chaque étape.

#### Vu globale sur les tâches de Développement à réaliser
