# STYLE — Écho · direction Sable

> **VERROUILLÉ (`/lock`) le 2026-11-18.** Validé par Gaia à partir de `planches/v3/01-sable.html`. Plus d'exploration de style : toute modification passe par `/delta` et une nouvelle entrée datée dans `DESIGN.md`.
> Référence pour toutes les pages. Desktop seul (1440 × 900), post de 760 × 620.

## 1. Principe

Le post est **un jardin de sable vu du dessus, en lumière rasante**. Rien n'est posé *sur* l'écran : tout est **creusé, imprimé ou posé dans** le sable. Pas de fond uni, pas de carte flottante, pas d'ombre décorative. Les seuls objets qui ont une ombre portée sont des objets physiques : galets et bouton de basalte.

Deux gestes structurent tout :
- **Le râteau** organise : sable ratissé droit hors des zones de jeu, trace à 3 dents comme séparateur.
- **La pierre** joue : un ping est un galet posé, ses ondes se creusent dans le sable, le sillon de l'écho est plus profond que les autres.

## 2. Lumière (fixe, ne jamais changer)

| Paramètre | Valeur |
|---|---|
| Direction | azimut **225°** (vient d'en haut à gauche), élévation **38°** |
| Relief | `feDiffuseLighting` sur une carte de hauteur (alpha), flou 2.1, `surfaceScale` 3.2, posé en `overlay` puis en `soft-light` |
| Soleil | dégradé radial `#fff6e3` à 55 % en haut à gauche |
| Ombres de fenêtre | 2 bandes en biais `#a4865f`, flou 28, `multiply` à 55 % |
| Vignette | `#4a3018` à 32 % sur les bords |
| Grain | bruit fractal 0.85, à 50 % |

## 3. Palette

| Rôle | Hex | Usage |
|---|---|---|
| Sable | `#dccaa6` | fond unique de tout le post |
| Lumière | `#fff6e3` | soleil, liserés des textes pressés |
| Encre (ombre profonde) | `#2b2119` | texte principal, chiffres |
| Encre 2 | `#5b4a38` | texte courant |
| Encre 3 | `#6e5940` | étiquettes mono |
| Encre 4 | `#8a7458` | étiquettes secondaires |
| Bande d'ombre | `#a4865f` | ombres de fenêtre, colonnes en creux |
| **Terre cuite** (accent unique) | `#b4472a` | **ce qui se passe maintenant** : onde en cours, « toi », nouveau galet, objet révélé |
| Terre cuite claire | `#d0623f` | anneau du bouton (sur fond basalte) |
| Galet | `#857261` → `#3b3026` → `#1d1611` | dégradé radial des galets |
| Basalte | `#54463a` → `#2a211a` → `#18120e` | bouton principal |
| Texte sur basalte | `#f3e9d6` | |

Règle : **une seule couleur d'accent**, la terre cuite, et seulement pour l'état présent. Jamais deux éléments en terre cuite qui se disputent l'attention, sauf l'onde et son galet.

## 4. Typographie

Polices libres OFL, embarquées (CSP Devvit) : **Unbounded** (linéale large) et **Geist Mono**. Licences dans `licences/`.

| Rôle | Police | Taille / graisse | Détail |
|---|---|---|---|
| Titre imprimé (`écho`, gros chiffres de résultat) | Unbounded | 62 / 600 | minuscules, approche −2, **imprimé en creux** dans le sable |
| Chiffre héros (distance, série) | Unbounded | 31 / 300 | approche −0.03em, unité en 13 / 400 |
| Règle du jeu | Unbounded | 15 / 300, phrase clé en 500 | interligne 1.42 |
| Texte courant | Unbounded | 12 / 300, chiffres en 600 | interligne 1.5 |
| Bouton | Unbounded | 12 / 500 | capitales, espacement 0.12em |
| Étiquettes | Geist Mono | 10.5 | capitales, espacement 0.18em |
| Cotes sur le sable | Geist Mono | 11 | sur pastille `#efe4cd` à 86 % |

Texte **pressé** (tout texte posé sur le sable) : liseré clair `1px 1px 0 rgba(255,247,232,.55)` + ombre `-.5px -.5px 0 rgba(70,45,20,.22)`.

## 5. Grille du post (760 × 620)

- Marge extérieure : **24**.
- **Plateau** (colonne d'information) : sable lissé et surélevé, coins 18. Largeur 252 dans la vue de jeu (contenu de 214 à x = 44) ; peut s'élargir dans les autres vues.
- **Salle** : carré de **420**, x = 310, y = 112 (10 m → 42 px/m) ; règle `0 — 10 M` au-dessus.
- Gouttière plateau / salle : 34.
- Hors plateau et salle : sable ratissé droit, un sillon tous les **10 px**.
- Rythme vertical dans le plateau : séparateurs « râteau » (3 sillons, pas de 8) entre les blocs.

## 6. Composants

| Composant | Description |
|---|---|
| **Plateau** | rectangle de hauteur 0.6 dans la carte de hauteur ; ses creux (titre, râteau) sont découpés au masque. |
| **Titre imprimé** | texte découpé dans le plateau + teinte `#3a2614` à 50 % dans le creux pour la lisibilité. |
| **Trace de râteau** | 3 sillons parallèles, trait 2.2, espacés de 8. Séparateur unique : pas de filet, pas de bordure. |
| **Galet (ping)** | ellipse 24 × 19, dégradé galet, reflet `#fff6e6` à 28 %, ombre portée (4, 5, flou 2.6). Numéro en Geist Mono à côté. |
| **Ondes** | cercles en creux tous les 10.5 px, qui s'estompent avec la distance ; **sillon d'écho** plus large (6) et plus profond, au rayon mesuré. |
| **Empreinte** | ping restant : creux vide de la forme d'un galet. |
| **Rangée de galets** | série (7 jours) et pings : galets pleins = faits, empreintes = à venir, anneau terre cuite = en cours. |
| **Cote** | point + pastille claire + distance en mono, accrochée au sillon (jamais sur l'objet caché). |
| **Bouton basalte** | pilule 50 de haut, dégradé basalte, ombre portée double, anneau terre cuite à gauche. Un seul par vue. |
| **Colonne de sable** | (graphiques) bosse de hauteur 1 sur le plateau : les données sont **modelées** dans le sable. |
| **Salle miniature** | la salle d'un jour passé, réduite, avec ses propres ondes (historique). |

## 7. Mouvement

| Quoi | Comment |
|---|---|
| Onde en cours | 3 fronts décalés de 1.1 s, rayon 6 → 1.15 × salle, **3.3 s linéaire**, s'efface ; doublée d'un fil terre cuite 1.4 px. |
| Écho revenu | le sillon d'écho se creuse (profondeur 0 → 1, 600 ms, ease-out), puis la cote apparaît. |
| Pose d'un galet | échelle 0.6 → 1 et l'ombre s'allonge, 400 ms, ease-out. |
| Nouveau jour de série | le 7ᵉ galet tombe dans son empreinte, anneau terre cuite qui pulse 1.2 s. |
| Le reste | **immobile**. Pas de parallaxe, pas de rebond, pas de transition décorative. |

## 8. États

| État | Rendu |
|---|---|
| Au repos (post dans le feed) | salle lisse, une seule onde lente au centre comme invitation, bouton « Start listening ». |
| Écoute | galet + onde terre cuite, relevé « listening » en terre cuite. |
| Écho revenu | sillon d'écho + cote, relevé en encre. |
| Pings épuisés | plus d'onde ; le bouton « Mark the object » reste le seul appel. |
| Objet révélé (fin) | creux terre cuite à l'emplacement de l'objet, marqueur du joueur relié par un trait et une cote d'écart. |
| Vide / erreur | jamais d'écran vide : sable ratissé + phrase pressée en Unbounded 15. |

## 9. Interdits propres à ce style

- Fond uni, carte blanche, ombre portée sur un bloc de texte.
- Deuxième couleur d'accent, dégradé coloré.
- Serif, police système, emoji.
- Filets et bordures pour séparer : utiliser la trace de râteau.
- Changer la direction de la lumière d'une vue à l'autre.
