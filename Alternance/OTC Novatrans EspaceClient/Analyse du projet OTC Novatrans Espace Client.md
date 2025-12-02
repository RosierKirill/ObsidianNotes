Questions avant d'analyser :

- Architecture : back et front
- bdd
- les pipelines (et leurs les taches)
- les repos


### 1) Le Repos



OTC Novatrans EspaceClient Front (Angular)


fonctionnalité mot de passe oublié : envoit sur mail (fonctionne en localhost)

Composants :

Auth
Home
NavBar


Services :

reference tables
goods
crud
history
cart(gerer les commandes au panier)
news
reservation
pay(payer la commande)
account (gerer les cpomptes)
contacts (liste des contacts)


si je comprends bien le systeme est assez classique - nous avons des composants qui gerent des pages et ces composants sont alimentés par des services qui eux utilisent les models. les models viennent du back.


pour ce qui est du back : il utilse deux choses : api db2 (l'api pour la bdd) et le core (permet de transformer les entities en model)

Test du front en integration 01/10/2025

quelques problemes de recuperetion de ressources (erreur 401 lors de la recuperation des ressources)

"news" correspond à la page d'accueil ou les news sont ajoutés

