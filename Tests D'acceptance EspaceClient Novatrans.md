
**En tant qu’** administrateur novatrans,  
**je veux** pouvoir gérer la table de référence des colis (ajouter, modifier, supprimer des lignes),  
**afin de** maintenir une liste à jour des types de colis utilisés dans le système.

---

### 

---

### ✅ **Colonnes présentes sur la page**

- **Libellé**
- **Image**
- **Action**

---

### ✅ **Ajout d'un colis**

- **Libellé (obligatoire)**
- Choisir un fichier

### **Critères d’acceptation**

1. **Affichage** : La page doit afficher la liste des colis avec les colonnes Libellé, Image, et les actions disponibles.

2. Plus de colonne ordre mais possibilité de faire du drag'n drop pour ordonner les lignes.
3. possibilité de filtrer et trier par colonne

4. **Ajout** : L’utilisateur peut ajouter une nouvelle ligne avec un libellé et éventuellement une image:

5. Limiter la taille des images à télécharger à 1mo.
6. présence d'un bouton pour pouvoir uploader les images. "Charger une image".

7. **Modification** : L’utilisateur peut modifier les informations d’une ligne existante.
8. **Suppression** : L’utilisateur peut supprimer une ligne existante.
9. **Pagination** : La liste doit être paginée  25 éléments par page.
10. **Validation** : Les champs obligatoires doivent être validés (ex. Libellé non vide). Le libellé ne doit pas déjà exister.
11. **Confirmation** : Une confirmation est demandée avant la suppression.


# Action 1 : Gestion des Tables de Référence

US62151
### Règles

| **Code** | **Contenu**                                                                                                                |
| -------- | -------------------------------------------------------------------------------------------------------------------------- |
| 0001     | **Affichage** : La page doit afficher la liste des colis avec les colonnes _Libellé_, _Image_, et les actions disponibles. |
| 0002     | Suppression de la colonne _ordre_ mais possibilité de réorganiser les lignes via **drag'n drop**.                          |
| 0003     | Possibilité de **filtrer** et **trier** par colonne.                                                                       |
| 0004     | **Ajout** : L’utilisateur peut ajouter une nouvelle ligne avec un libellé et éventuellement une image.                     |
| 0005     | Limiter la taille des images téléversées à **1 Mo**.                                                                       |
| 0006     | Présence d’un bouton pour uploader les images : **"Charger une image"**.                                                   |
| 0007     | **Modification** : L’utilisateur peut modifier les informations d’une ligne existante.                                     |
| 0008     | **Suppression** : L’utilisateur peut supprimer une ligne existante.                                                        |
| 0009     | **Pagination** : 25 éléments par page.                                                                                     |
| 0010     | **Validation** : Champs obligatoires validés (libellé non vide, libellé unique).                                           |
| 0011     | **Confirmation** : Une confirmation est demandée avant la suppression.                                                     |
### Tests d'Acceptance


---

**0001 – 001-A**  
**given** Je suis sur la page de référence  
**when** Je choisi la table de référence "colis"  
**then** Je voit apparaître le tableau avec les champs Libellé, Image et Action

---

**0002 – 002-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** Je déplace une ligne  
**then** L'ordre des référence change

---

**0003 – 003-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** J'appuis sur l'entête d'une des colonnes  
**then** la table est triée en fonction de cette colonne

---

**0003 – 003-B**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** J'appuis sur l'entête de deux colonnes  
**then** la table est triée en fonction de ces deux colonnes

---

**0004 – 004-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** Je clique sur "Ajouter une ligne"  
**then** Je peux remplir le champs Libellé et selectionner importer une image.

---

**0005 – 005-A**  
**given** Je suis sur la page de création de ligne  
**when** Je clique sur Choose File, et j'importe le fichier  
**then** Le fichier importé ne peux pas dépasser 1 Mo

---

**0006 – 006-A**  
**given** Je suis sur la page de création de ligne  
**when** Je regarde la page  
**then** Je dois voir le bouton Choose File

---

**0007 – 007-B**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** J'appuis sur le bouton Modifier la ligne  
**then** Je dois pouvoir modifier le Libellé et l'image de cette ligne

---

**0008 – 008-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** J'appuis sur le bouton Supprimer la ligne  
**then** La ligne doit être supprimée

---

**0009 – 009-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** Je regarde la page  
**then** Il doit avoir 25 éléments par page.

---

**00010 – 0010-A**  
**given** Je suis sur la page d'ajout d'une ligne et le champs Libellé est vide  
**when** Je veux valider la ligne  
**then** Le bouton valider est indisponible et je ne peux pas valider

---

**00010 – 0010-B**  
**given** Je suis sur la page d'ajout d'une ligne et je rempli le champs Libellé avec un nom déjà existant  
**when** Je veux valider la ligne  
**then** Une erreur s'affiche et je ne peux pas valider

---

**00011 – 0011-A**  
**given** Je suis sur la page de référence, avec la table colis sélectionnée  
**when** J'appuis sur le bouton Supprimer la ligne  
**then** Un popup de confiramtion s'affiche pour confirmer la suppression

---
