# REFS — Écho

> Décodage au premier passage, 2026-11-18. On prend des **principes**, jamais un layout, un texte, un asset, une police ou une marque.

## Igloo — igloo.inc

**Ouverture** : site ouvert le 2026-11-18 dans le navigateur intégré. La scène WebGL principale ne s'est pas chargée dans cet environnement (le site reste sur son écran de chargement après ~25 s et une interaction). Ce que j'ai pu observer directement :

- Écran de chargement : un fond uni froid et désaturé (gris bleuté, `rgb(160,165,177)`), un seul élément au centre — une ligne fine faite de caractères qui se remplit. Rien d'autre à l'écran.
- La page ne contient quasiment pas de texte HTML : tout passe par la lumière et la matière dans la scène 3D.

**Ce que je retiens (principes)** :
1. **Un seul élément vivant à l'écran à la fois.** Le reste est silence. → Dans Écho, l'onde en cours est le seul élément animé.
2. **La lumière est la couleur.** Pas d'aplats colorés : la couleur n'existe que là où quelque chose émet. → L'accent n'apparaît que sur ce qui « sonne » (ping, anneau, retour).
3. **Le chargement est déjà de l'identité** : un indicateur fait de traits fins plutôt qu'un spinner générique. → Nos états d'attente (onde en vol) sont dessinés dans le même langage que le jeu.

**Limite** : la profondeur sombre de la scène 3D n'a pas pu être vérifiée visuellement ici ; je ne la cite pas comme observée. À revoir sur une machine où la scène se charge.

## Psychoactive — psychoactive.co.nz

**Ouverture** : site ouvert le 2026-11-18, page d'accueil + défilement.

**Observé** :
- Fond quasi noir légèrement chaud (`rgb(16,16,18)`), texte blanc.
- Couleur saturée uniquement dans une zone (le média/reel au centre, irisé) ; tout le reste est monochrome.
- Typo : une grotesque à très grand corps, chasse serrée (approche négative marquée sur les titres), poids normal, à côté de micro-étiquettes en capitales espacées, style mono, qui portent des coordonnées et des durées.
- Repères fins (petites croix / points) aux coins des zones, comme des marques de cadrage.

**Ce que je retiens (principes)** :
1. **Saturation concentrée** : une seule zone saturée par écran, sur un fond très sombre. Le reste en blanc à opacités dégressives.
2. **Contraste d'échelle** : un chiffre énorme + des micro-étiquettes mono. → Le retard (ms) peut être le héros typographique.
3. **Les données comme décor** : coordonnées et durées affichées en mono deviennent un ornement qui a du sens. → Chez nous, ce sont de vraies mesures (x/y, ms, m).
4. **Marques de cadrage** aux coins plutôt que des bordures pleines.

**Non repris** : layout, textes, police (Roobert, sous licence), reel, logo, irisation.

## Contraintes techniques héritées

- CSP Devvit : aucune requête externe → polices **embarquées** en production. Les planches V1 utilisent des piles de polices système ; le choix des fontes (licence libre type OFL) se fera dans `STYLE.md` une fois la direction validée.

---

## V2 — 2026-11-18 — références games (`narratif-jeu`)

Source : `REFERENCES-DESIGN.md` et captures `REFERENCES-CAPTURES/narratif-jeu/` du dépôt `hackatons-pipeline`, demandées par Gaia après le rejet de V1. Les 10 captures ont été lues, ainsi que la capture d'Igloo (`3d-matiere/igloo.inc.png`), qui comble la limite notée plus haut.

### Diagnostic V1
Les trois planches V1 étaient des **interfaces posées sur un fond uni** : grille, cercles, panneau de relevés, polices système. Aucune des refs games ne fonctionne comme ça : chacune a d'abord un **monde physique** (un objet, une matière, une lumière qui vient de quelque part), et l'interface vient se loger dedans.

### Ce que chaque ref apporte (principes, pas de layout)

| Ref | Observé | Principe retenu |
|---|---|---|
| Don't Look Up (jeu) | Papier blanc cassé, encre noire épaisse, petits personnages au trait, bulles « whatever », titre dessiné énorme, boutons noir/blanc avec ombre décalée dure. | Le trait à la main **est** l'identité ; les bulles donnent une voix aux éléments ; bouton à ombre décalée. → **02 Encre** |
| Gemeos | Papier crème grainé, stickers à contour blanc et ombre, flèches et gribouillis à la main, titre très gras. | Stickers (contour + ombre) pour les données ; gribouillis comme ponctuation. → **02 Encre** |
| Gapsy Studio | Lettres en relief dans une pièce blanche, lumière rasante qui projette des ombres de fenêtre en biais, annotations manuscrites. | **Lumière rasante + ombres portées** : le relief se lit grâce à la direction de la lumière. → **01 Sable** |
| Raben Rifaie | Beige chaud, lumière douce d'une fenêtre, serif italique de grande taille, paysage minéral (pierres, eau). | Palette minérale chaude, serif italique en héros, calme. → **01 Sable** |
| Igloo | Objet unique rendu en 3D, lumière froide, étiquettes de données reliées à l'objet par des filets fins. | Un seul objet éclairé ; **callouts** de données accrochés à la matière. → 01 (cotes sur les sillons) et 03 |
| MemoryQuest | Borne d'arcade : objet physique centré, écran à motif concentrique lumineux, boutons lumineux, halo coloré derrière. | **Le jeu est un appareil** : écran dans une coque, voyants, gros bouton. → **03 Phosphore** |
| Experience Funtech | Scène nocturne, néons, anneau lumineux autour du personnage, info-bulle « Hold to dance ». | Anneau lumineux comme signe ; lumière émise qui éclaire la matière autour. → **03 Phosphore** |
| Matchball | Objets (ballons) photoréalistes en héros, titre condensé très gras, fond blanc. | Objets réels en héros, typo condensée affirmée. → titre de 03 |
| Sponge | Créature 3D dans une brume rouge, monochrome. | Une seule teinte + brume. Non retenu (horreur, hors ton). |
| Dairy Food Bulgaria / Merci Studio | Île 3D surchargée ; aplat dégradé + arches 3D. | Non retenus : surcharge / dégradé criard (interdits du brief). |

### Faisabilité « budget léger »
Tout est reproduit en SVG + CSS, sans 3D : relief = `feDiffuseLighting` sur une carte de hauteur ; trait qui bout = `feTurbulence` animée + `feDisplacementMap` ; phosphore = flou additif + trames. Rien qui ne tienne pas dans un post Devvit.
