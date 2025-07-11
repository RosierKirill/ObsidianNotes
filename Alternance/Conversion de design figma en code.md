***openai token
magicien
integrer avec figma

***faire une présentation sur ce sujet




## Tout d'abord les test avec quelques plugins pour figma :

Resumé du test de chaque plugin.

**Sommaire des plugins testés :

- Code Generator - CodingScape
- Kiwi.ui Generate Figma to Front-end code
- *Tailwind React Code Generator - Pagesoft
- 

### 1. Code Generator - CodingScape

Ce plugin demande de choisir le type de technologie à utiliser ainsi que la clé Api de OpenAi

J'ai récupéré ma clé api sur mon compte OpenAi :

	XXXXXXXXXX

Erreur.
### 2. Kiwi.ui Generate Figma to Front-end code

Génère du code à partir des éléments du design mais il faut les nommer selon les principes demandés (\_\_btn pour un bouton, \_\_C pour un composant)

-> En résultat nous avons un .zip mais qui se retrouve vide, et si on l'ouvre avec vscode, on trouve un message "message{emojis}"
### 3. Tailwind React Code Generator - Pagesoft :

- Génére du code brut .jsx et css à partir d'un élément du design

Utilisation -> selectionner un élément par exemple une section avec des composants; résultat -> deux codes générés .jsx et .css; on peut le copier

Nuance avec ce plugin : il faut nettoyer et adapter le code fourni car tel quel il peut etre incopatible dans un projet Angular ou React; il semble aussi être très verbeux, notamment la partie .css et utilisant des des balises peu adaptables (aspect-ratio)

### 4. Codima Ai Powered Code Generator

Le code se génère assez facilement :
- se connecter au compte (par exemple github)
- cependant il faut avoir des token, qu'on doit acheter.
-> Observation : Codigma a une application à part qui peut servir de designer comme Figma

#### 5. Figmular : Export Figma to Angular components

- Un plugin spécifiquement fait pour convertir Figma en Angular
- on peut avoir le code html, css et js; 
- ce plugin travail avec codesandbox.io pour tester rapidement le code généré sur une page web.
- on peut avoir une preview du composant généré
- Trial disponible seulement pour 7 jours
- le code généré reste à retravailler/ n'est pas fonctionnel tel quel

### 6. Magician 

- Ce plugin ia sert surtout à générer les images, icônes, ou le texte pour le design.
- Il ne génère pas de code.
- Il faut avoir un clé d'accès
#### Reste à explorer :

- Coder sa propre api;

- Utiliser l'API de Figma pour avoir un acces aux maquettes dans le code;
- A remettre à plus tard.


#### Recherche des plugins :


| Nom du plugin                                          | Remarques                                                                                               | Efficacité | Utilité |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- | ---------- | ------- |
| Code Generator - CodingScape                           | Il faut le token openai                                                                                 | aucune     | aucune  |
| Kiwi.ui Generate Figma to Front-end code               | génère un dossier vide                                                                                  | aucune     | aucune  |
| Tailwind React Code Generator - Pagesoft               | Code à retrvailler ou inadapté                                                                          | aucune     | aucune  |
| Codigma Ai Powered Code Generator                      | il faut payer les prompts                                                                               | aucune     | aucune  |
| Figmular : Export Figma to Angular components          | Trail de 7 jours seulement                                                                              | faible     | aucune  |
| Magician                                               | Génère les images; il faut le token openai                                                              | faible     | moyen   |
| Tempo - Ai Powered Figma to Code                       | il y a 5 prompts par jour; code à retravailler                                                          | moyen      | moyen   |
| AWS Amplify UI Builder                                 | genere du code                                                                                          | aucune     | aucune  |
| LiveDesign                                             | Pour React; Code à revoir                                                                               | moyen      | faible  |
| Bricks - AI Powered Design to Tailwind                 | Pour React; 3 essai par jour; Fonctionne pas;                                                           | aucune     | aucune  |
| CSS Generetator                                        | genere le code css et html d'un element                                                                 | moyen      | moyen   |
| FFIT Laum                                              | écrire du code dans figma et ajouter des scripts/fonctions                                              | faible     | aucune  |
| Huima                                                  | Genere le html                                                                                          | moyen      | moyen   |
| Figma Raw: Export Design Data                          | genere un JSON qui decrit le design de figma pour les IA generatives                                    | moyen      | aucune  |
| Codex - Repository-Aware Code Generator powered by Ai  | Il n'y a que 5 crédits gratuits; marche une fois sur deux;  le code est à tester; besoin d'un repo git; | faible     | faible  |
| 10x HTML \| Design to clean responsive code x10 faster | genere du code HTML/CSS; preview on peu pas copier;                                                     | bien       | moyen   |
| fastr Exporter                                         | permet d'exporter le design figma en svg                                                                | aucune     | aucune  |
| Design to JSON                                         | genere pas de json - erreur pas claire                                                                  | aucune     | aucune  |
| Locofy Lightning                                       | il faut s'inscrire pour un plan                                                                         | aucune     | aucune  |
