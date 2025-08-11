



## Contexte

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
- **15 pays :** *dans différentes filiales, dans quasiment toutes les régions de France et certaines à l'international (Europe et Maroc)*
- **Service d'Informatique** : DSI (Direction Systèmes d'Information)

	![[Carte Europe GCA.png]]


## Le Besoin Concret


GCA a de nombreuses applications pour répondre aux diverses besoins du métier. L'équipe technique qui s'occupe du déploiement et maintien de ces applications peut faire du monitoring de toutes ces applications avec des interfaces dédiés (ArgoCD, Longhorn) 

Mais il y a deux problèmes :

1. les interfaces sont nombreuses et fournissent des informations sur différentes applications dans les environnement différents (Production et Hors Production).
2. Ces interfaces fournissent un grand nombre d'informations qui sont pas toujours utiles pour l'utilisateur

De là découle le besoin concret de créer une application centralisée, donc qui montre toutes les applications et leur versions peu importe l'environnement. Simple et intuitive, donc qui affiche que les informations pertinentes dans une interface facilement accessible, Le Dashboard GCA.

## Dashboard


Pour expliquer plus clairement l'utilité des Dashboard pour le suivis des applications, je souhaiterais illustrer cet enjeux par une petite métaphore :

Jean est un fermier avec 10 vaches, il les connais et leur attribue a chacune un nom.
Cependant si Jean décide d'agrandir son troupeau jusqu'à 1000 vaches il aura du mal à garder tous leurs nom en tête et donc aura besoin d'un outil numérique qui pourra dynamiquement gérer son immense troupeau grâce aux identifiants par exemples. 

## Objectifs du Projet


Comment concevoir un outil centralisé, accessible et intuitif, permettant à tous les profils – techniques comme non techniques – de visualiser en temps réel les applications déployées et leurs versions associées ?


##  Partie Technique


La technologie clé de ce projet (comme de la grande partie des projets gérés par l'équipe) est Kubernetes.

Pour faire simple Kubernetes est un orchestrateur des conteneurs d'applications.

Et pour l'expliquer au mieux je vous propose de prendre l'illustration d'un vrai orchestre :

Ci dessus on voit les principaux éléments de Kubernetes avec l'équivalent méthaphorique qu'on peut leur attribuer :

- *Cluster*, le groupe entier = l'orchestre en entier
- *Node* (nœud), un ordinateur (machine) = le musicien
- *Pod*, la plus petite unité Kube = l'instrument de musique
- *Container*, contient le programme = la musique
## Démarche Projet

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

---

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

**Au contrario ce que j'ai apporté à l'entreprise :**

- Un outil simple et efficace pour visualiser les applications et leur versions
- Des questionnement sur la documentation et les ressources internes à l'équipe transverse (une documentation sur l'appli Dashboard par exemple)
