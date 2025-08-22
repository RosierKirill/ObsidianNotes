##### Présentation de la soutenance de stage

## Qui suis-je?

- *Kirill ROSIER, alternant développeur*
- *étudiant en 3ème année de BUT MMI*
- *Durée 12 mois d'alternance : 02/09/2024 - 02/08/2025, le rythme de 2 semaines d'école et 2 semaines d'entreprises.*

## Entreprise :


- **Nom** : *Groupe Charles André, Montélimar* 27000
- **Activités** : *Transport & Distribution, Logistique Automobile, Logistique Industrielle, Opérateur de Transport combiné, Lavage et Dépôt*
- **Effectif :** 10 000 employés
- **Chiffre d'affaires :** 1.8 milliards €
- **Implantation :** 150 filiales.
- **15 pays :** Europe et Maroc
- **Service d'Informatique** : DSI (Direction Systèmes d'Information)

	![[Carte Europe GCA.png]]


## Le Besoin Concret


GCA a de nombreuses applications pour répondre aux diverses besoins du métier. L'équipe technique qui s'occupe du déploiement et maintien de ces applications peut faire du monitoring de toutes ces applications avec des interfaces dédiés (ex. Rancher)

Mais il y a deux problèmes :

1. les interfaces sont nombreuses et fournissent des informations sur différentes applications dans les environnement différents (Production et Hors Production).
2. Ces interfaces fournissent un grand nombre d'informations qui sont pas toujours utiles pour l'utilisateur

De là découle le besoin concret de créer une application centralisée, donc qui montre toutes les applications et leur versions peu importe l'environnement. Simple et intuitive, donc qui affiche que les informations pertinentes dans une interface facilement accessible. C'est le Dashboard de GCA.

## Dashboard


Pour expliquer plus clairement l'utilité des Dashboard pour le suivis des applications, je souhaiterais illustrer cet enjeux par une petite métaphore :

Un fermier avec 10 vaches, il les connais et leur attribue a chacune un nom.
Cependant si le fermier décide d'agrandir son troupeau jusqu'à 1000 vaches il aura du mal à garder tous leurs nom en tête et donc aura besoin d'un outil numérique qui pourra dynamiquement gérer son immense troupeau grâce aux identifiants par exemples. 

## Objectifs du Projet


Comment concevoir un outil centralisé, accessible et intuitif, permettant à tous les profils – techniques comme non techniques – de visualiser en temps réel les applications déployées et leurs versions associées ?


##  Partie Technique


La technologie clé de ce projet (comme de la grande partie des projets gérés par l'équipe) est Kubernetes.

Pour faire simple Kubernetes est un orchestrateur des conteneurs d'applications.

Et pour l'expliquer au mieux je vous propose de prendre l'illustration d'un vrai orchestre :

Ci dessus on voit les principaux éléments de Kubernetes avec l'équivalent métaphorique qu'on peut leur attribuer :

- *Cluster*, le groupe entier = l'orchestre en entier
- *Node* (nœud), un ordinateur (machine) = le musicien
- *Pod*, la plus petite unité Kube = l'instrument de musique
- *Container*, contient le programme = la musique

Partant de là on peut approfondir :

- L'utilisateur métier a besoin de visualiser les applications et leur versions dans les différents environnements
- 
## Démarche du Projet

### Étapes de Réalisation :

- Introduction au projet Dashboard version Kubernetes Client
- Analyse du projet
- Présentation de mon analyse à l'équipe
- Plan d'action pour l'amélioration
- Présentation du plan d'action puis les consignes de la part de l'équipe
- Refonte du concept de base (utilisation d'une autre techno, ArgoCD API)
- Suivi des modifications journalier, consultations avec l'équipe, soutien dans le développement
- présentation, un point sur la première version
- Revue de code, commentaires
- Prise en compte des remarques, modifications de l'application
- Nouvelle présentation, validation par l'équipe

Remarque : on met l'accent au départ (et tout le long de l'alternance) sur :
- la formation
- la communication avec l'équipe

## Intégration à l'équipe

- Apprentissage des technologies spécifiques utilisé dans l'équipe.
- Communication régulière en Daily, présentations en tête-à-tête. 
- Evaluation et validation des maquettes Figma pour le visuel
- Des revues de code pour plus de techniques. 
- Questions

## Le Bilan Personnel de l'Alternance


**Apports d'école :**

- Connaissances techniques de base (languages, technologies)
- Théorie sur le travail en entreprise
- Réalisation de projets

**Apports entreprise :**

- Mise en pratiques des connaissances
- Expérience de travail concrète
- Travail en collaboration
- Approfondissement des compétences techniques
- Introduction au domaine de CI/CD, inconnu pour moi

Ce que j'ai apporté à l'entreprise :

- Un outil simple et efficace pour visualiser les applications et leur versions
- Des questionnement sur la documentation et les ressources internes à l'équipe transverse (une documentation sur l'appli Dashboard par exemple)


Remarques :

-> préciser un peu les métiers(FAIT)

par exemple - log auto : carrosserie ou mécanique
t&d : camions citernes
lavage : lavage des citernes
log indus. : entreposage

<<passage à l'échelle>>(FAIT)


schéma du besoin : au lieu de "cluster" mettre métier; mettre plusieurs utilisateurs métier; préciser que c'est plus grand que "3 clusters", montrer le côté désordre qu'il faudrait ranger

la problématique est trop longue et complexe (FAIT)

présenter les gens de l'équipe (FAIT)

 et leurs rôle : manager, architecte, RM dev (FAIT)

faire une vidéo de Dashboard ()

le sommaire a revoir :
grande partie/ petite partie (FAIT)

Démonstration :

Fonctionnalités :

- Métier
- Filtre
- Comparaison


dynamiser le script : faire en une phrase ce qui est illustré par les slides; rendre plus fluide - moins "liste"

expliquer plus la notion du passage à l'échelle : d'ou proviendrait le besoin de utiliser les outils de suivis ( au début les applications ont été plus faciles à suivrais (exemples de 2 application Ecar à 10))

NOT found - expliquer comment les versions sont récupérés

Pourquoi l'utilisateur final aurait besoin d'utiliser Dashboard : l'utilisateur métier a besoin d'accéder

expliquer kubernetes avant de montrer le besoin

ajouter des légendes

citer que les prenoms de l'equipe, preciser les roles et expliquer avec qui j'ai été le plus en contact

pour les metiers il faudrait rendre plus dynamique (mettre des photos exemples) il faut que les activités de l'entreprise soit bien clair



pour le schema d'applications 

mettre des application et leurs versions bien differentes (AppSupply)

revoir problematique et objectif -> combiner peut etre



justifier l'utilisation des technos

faire ressortir la premiere version du projet dashboard 

pour la demarche du projet -> frise chronologique?
début du developpement -> plutot concept

montrer 'améliioration' le feedback et modifications

refaire la video plus lentement (parler dans la tete durant l'enregistrement)

expliquer les noms et les version -> il y a un travail a faire coté devops

pour les questions jurys : entamer des sujet mais faire attentions 

approfondir - les apport pour moi / entreprise (exemples concrets au lieu de lire le tableau) ; developpement du projet => devops 

faire le durant la presentations



le status de l'application : defini par argocd; on a pas la main sur

healthy : les ressources sont deployés correctements, et les pods doivent etre considéré healthy, healthcheck (test de santé) -> endpoint spécifique (prob<-kubernetes)

out of sync - ecart entre le déployé et l'application réelle, 

uknown : des erreurs de configuration l'application n'est pas forcement ne marche pas

degraded : le healthcheck ne passe pas

