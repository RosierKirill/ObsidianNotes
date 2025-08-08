Tous les éléments fait et à faire :

Partie Back :

Fait

- récupération des noms des projets
- récupération des noms des applications
- récupérations des namespaces (es ce que c'est utile?)
- //versions (à vérifier)
- //métiers (à vérifier)
- méthode de remplissage du dto dans versionService
- sérialisation vers json et exposition sur l'endpoint pour le front (modifier pour le déploiement)
- connexion au client kubernetes creation d'un deployement avec dockerdesktop et lens

A faire :

- classe ApplicationRessources pour la recupération de toutes le resources ()
- des classes ressources (notamment pour les version si besoin)
- test et testNative fonctionnel
- Template http (si besoin)

Partie Front :

Fait :

- affichage de la liste des application
- header
- navigation bar sur le côté gauche
- fonction de filtre par nom et environnement
- groupe d'application par nom de projet
- affichage de détail 
- changement de vu list/grid
- fonction de couleur en fonction de l'environnement (dégradé de bleu)

A faire :

- test et test native
- tri par métiers (voir comment récupérer les métiers)
- revoir le code (back et front) en reprenant le code de dashboard kubernetes
-  fonction de comparaison de versions (à finir)