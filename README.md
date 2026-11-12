# Catalogue d'images de L'atelier de Mila

Ce dépôt ne contient que les images des nouveautés de l'application : coiffures, vêtements et décors ajoutés
après coup, sans mise à jour de l'application. Il est public, pour que l'application puisse télécharger les
images directement.

```
coiffures/   nouvelles coiffures
vetements/   nouveaux vêtements et accessoires
decors/      nouveaux décors du Mode Scène
```

## Ajouter une image

1. Ouvrir le dossier voulu, puis **Add file → Upload files**, déposer le PNG et valider (**Commit changes**).
2. Le lien direct de l'image suit toujours ce modèle :

   ```
   https://raw.githubusercontent.com/cmirault/latelier-de-mila-catalogue/main/<dossier>/<fichier>.png
   ```

   Exemple : `https://raw.githubusercontent.com/cmirault/latelier-de-mila-catalogue/main/decors/foret.png`

3. Coller ce lien dans le champ `imageUrl` d'un document de la collection Firestore `remote_catalog`.

Utiliser des noms de fichiers simples : minuscules, sans espace ni accent (`foret-enchantee.png`).

## Remplacer une image

L'application garde les images déjà téléchargées. Pour qu'une nouvelle version soit prise en compte, lui donner
un **nouveau nom** (`foret-2.png`) et mettre à jour `imageUrl`, plutôt que d'écraser l'ancien fichier.

## Format des images

| Type | Image attendue |
| --- | --- |
| Décor (`scene`) | PNG ou JPEG, affiché en plein écran et recadré ; prévoir un sujet centré, lisible en portrait comme en paysage. |
| Coiffure (`hair`) | PNG transparent, cheveux **blancs** au trait noir (ils prennent la couleur choisie). Sa place est donnée par `anchor` : `[x, y, largeur, hauteur]` dans le canevas du personnage (1004 × 1940). |
| Vêtement (`garment`) | PNG transparent. Blanc au trait noir s'il doit être recolorable ; déjà en couleurs avec `tintable` à `false` sinon. Sa place est donnée par `slot` et, si besoin, `bounds`. |
