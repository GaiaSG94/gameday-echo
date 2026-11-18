# DESIGN — Écho (journal)

> Tenu par Claude (directeur artistique). Versions datées, jamais écrasées.

## V3 — 2026-11-18 — Sable : zone gauche refaite

**Statut** : **les 4 pages sont validées** par Gaia le 2026-11-18 (Post, Jeu, Carte de fin, Séries & classement). **Style verrouillé (`/lock`) le 2026-11-18.**

### Retour de Gaia sur V2
Partie droite de Sable : bien. Partie gauche : à retravailler pour une vraie identité autour du sable, plus moderne ; la police serif fait vieillotte.

### Changements (`planches/v3/01-sable.html`)
- **Plus de dalle de pierre** : la zone gauche est un plateau de sable lissé, légèrement surélevé, qui fait partie de la même matière que la salle (relief calculé par la même lumière).
- **Titre « écho » imprimé dans le sable** (creux éclairé en lumière rasante), en minuscules.
- **Motif récurrent : la trace de râteau à 3 dents**, utilisée comme séparateur (titre / règle / relevés). Les petits textes sont « pressés » dans le sable (liseré clair en bas à droite, ombre en haut à gauche).
- **Typo moderne** : Instrument Serif → **Unbounded** (linéale large, titres, règle, distances), IBM Plex Mono → **Geist Mono** (étiquettes, ms). Licences OFL dans `licences/`.
- Relevés réorganisés : la distance en grand (`5.88 m`), le retard et le numéro d'écho en petit à droite.
- Bouton : galet de basalte sombre, texte en capitales espacées, anneau terre cuite.
- Partie droite (salle, pierres, sillons, cotes) **inchangée**, sauf la police des cotes (Geist Mono).

### Déclinaison (après validation de Gaia : « Oui, décline »)
- `STYLE.md` écrit : lumière, palette, échelle typo, grille, composants, mouvement, états, interdits.
- Moteur de sable commun à toutes les pages (plateaux, creux imprimés, salles, ondes, galets, cotes), pour une continuité stricte.
- `planches/v3/02-post.html` — **Post** au repos : plateau avec titre imprimé, accroche, joueurs du jour, série, bouton « Start listening » ; la salle du jour ratissée en cercles autour du numéro **014** en relief, une onde lente comme invitation.
- `planches/v3/03-fin.html` — **Carte de fin** : écart en héros imprimé (`0.42 m`), pings utilisés, série passée à 7 (le nouveau galet pulse en terre cuite), « Better than 62 % », histogramme des pings du jour **creusé dans le sable**, aperçu de la ligne postée, bouton « Comment result », compte à rebours. La salle révèle l'objet (creux terre cuite) et le marqueur du joueur, reliés par l'écart.
- `planches/v3/04-series.html` — **Séries & classement** : onglets Room / Board ; série en héros imprimé (`7`), record ; les 7 dernières salles en **salles miniatures** avec leurs propres ondes, plus l'empreinte de demain ; distribution du jour creusée ; classement en texte pressé, la ligne du joueur en terre cuite.
- Données cohérentes entre pages : série 6 avant de jouer (Post, Jeu), 7 après (Fin, Board) ; 1 284 joueurs ; distribution 61 / 302 / 448 / 311 / 162 (médiane 4) ; rang 483 (≈ 62 %).

### Changelog
- 2026-11-18 · V3 · Sable : zone gauche refaite, Unbounded + Geist Mono. V2 conservée dans `planches/v2/`.
- 2026-11-18 · V3 · Sable validée. `STYLE.md` ; planches Post, Carte de fin, Séries & classement. Questions [H] 7 à 9 ajoutées dans `PAGES.md`.
- 2026-11-18 · V3 · Post, Carte de fin, Séries & classement validées par Gaia : toutes les pages ont leur planche validée.
- 2026-11-18 · **LOCK** · style Sable verrouillé. Référence : `STYLE.md` + `planches/v3/`. Fin des explorations ; v1 et v2 conservées pour l'historique.

## V2 — 2026-11-18 — Refonte : un monde, une matière, une typo

**Statut** : Sable retenue en direction pressentie (partie droite validée), poursuivie en V3. Encre et Phosphore non retenues.

### Retour de Gaia sur V1
« Slop IA » : matière, couleurs et motifs non travaillés, pas d'identité visuelle. Le mobile n'a pas lieu d'être sauf exigence du hackathon. Aller voir les références games.

### Décisions
- **Desktop seul** (1440 × 900). Vérifié : les critères du hackathon (`criteres/reddit-gameday-2026.md`) n'exigent pas le mobile ; le « mobile first » venait de `IDEE.md`. Cela remplace le §6 du brief.
- Références : les 10 refs `narratif-jeu` + la capture d'Igloo, analysées dans `REFS.md` § V2.
- Principe commun aux 3 directions : **le post est un lieu physique** (sable, papier, appareil) éclairé d'une direction précise ; l'interface est gravée, dessinée ou affichée **dans** ce lieu, pas posée dessus.
- **Polices libres (OFL) embarquées en base64** dans chaque planche, licences dans `licences/`. Plus aucune police système.
- Données de démo et hypothèses [H] inchangées par rapport à V1, pour que la comparaison porte uniquement sur le style.

### Les 3 directions
- `planches/v2/01-sable.html` — **Sable**. Jardin de sable ratissé, vu du dessus, en lumière rasante de fin de journée. Chaque ping est une pierre posée : les ondes sont creusées dans le sable (relief réellement éclairé), et le sillon de l'écho est plus profond que les autres. Hors de la salle, le sable est ratissé droit. Ombres de fenêtre en biais. Texte sur une dalle de pierre. Sable `#dccaa6`, ombre `#2b2119`, accent terre cuite `#b4472a` (seulement l'onde en cours). Instrument Serif (italique en héros) + IBM Plex Mono. Refs : Gapsy, Raben Rifaie, Igloo.
- `planches/v2/02-encre.html` — **Encre**. Carnet dessiné à la main, trait qui « bout » (tremble en continu, 8 images/s). La pièce a des murs hachurés ; chaque ping est une étoile « clap » numérotée ; l'écho répond dans une bulle « tok! 34.3 ms ». Données en stickers, série comptée en bâtons, le O du logo est une onde. Papier `#f4f1e9`, encre `#141414`, accent surligneur `#ffcf33` (onde en cours, ombre du bouton). Gluten + Patrick Hand. Refs : Don't Look Up, Gemeos.
- `planches/v2/03-phosphore.html` — **Phosphore**. La direction de départ (profond + sonar), devenue un appareil : écran cathodique rond dans une lunette vissée, graduations de gisement, échos qui rémanent (les plus anciens s'éteignent), trames de balayage, reflet sur le verre. À droite, une plaque de métal brossé avec afficheurs fluorescents, voyants de série et de pings, gros bouton lumineux « Mark the object ». Bakélite `#1c1b19`, verre `#04100f`, phosphore `#5eead4`. Big Shoulders + VT323. Refs : MemoryQuest, Funtech, Igloo.

### Changelog
- 2026-11-18 · V2 · V1 rejetée ; `REFS.md` complété (refs games) ; `PAGES.md` passé en desktop seul ; 3 nouvelles planches dans `planches/v2/` ; licences OFL ajoutées.

## V1 — 2026-11-18 — Exploration de style sur la page principale (Jeu)

**Statut** : **rejetée** par Gaia le 2026-11-18 (voir V2). Fichiers conservés dans `planches/v1/`.

### Livré
- `PAGES.md` : 4 pages proposées (Post, Jeu, Carte de fin, Séries & classement) + 6 questions produit ouvertes.
- `REFS.md` : décodage d'Igloo (partiel : la scène WebGL n'a pas chargé, seul l'écran de chargement a été observé) et de Psychoactive.
- 3 planches de la page **Jeu**, chacune avec les deux cadres côte à côte (1440 × 900 et 390 × 844), même salle de démo, même état, pour comparer le style et rien d'autre :
  - `planches/v1/01-sonar.html` — **Sonar** (direction de départ) : fond profond `#071a1f`, un seul accent lumineux `#5eead4` qui n'apparaît que sur ce qui émet ; sans large légère + mono ; anneaux concentriques qui s'estompent, retard affiché comme un repère sur une ligne de temps.
  - `planches/v1/02-trace.html` — **Trace** : quasi-noir `#111013`, blanc, un seul signal saturé `#ff3e8a` réservé à l'onde en cours et à l'action ; grotesque serrée à très grand corps (le retard en héros) + micro-étiquettes mono ; oscillogramme par ping, le pic d'écho placé à son retard.
  - `planches/v1/03-carte.html` — **Carte** (s'écarte de la direction de départ) : papier `#ece6d8`, encre `#1c242b`, vermillon `#e0452b` pour l'onde en cours ; serif de texte + mono ; relevé au compas sur une carte graduée, rayons annotés à la main.

### Données de démo (identiques sur les 3 planches)
Salle 10 × 10 m, objet en (6.4, 3.1) — non affiché. Ping 1 en (2.0, 7.0) → 34.3 ms / 5.88 m ; ping 2 en (8.5, 7.5) → 28.4 ms / 4.88 m ; ping 3 en (4.5, 2.0) en écoute. Retard = aller-retour à 343 m/s. Série de 6 jours, 1 284 joueurs du jour, médiane 4 pings.

### Hypothèses [H] utilisées sans décision produit
5 pings par salle · salle carrée fixe · un seul marqueur final. Voir `PAGES.md` § Questions.

### Décisions techniques
- Polices : piles système dans les planches (aucune requête réseau). Choix de fontes libres à embarquer → `STYLE.md` après validation.
- Planches générées en HTML autonome, CSS et JS inline, ouverture par double-clic.

### Changelog
- 2026-11-18 · V1 · création de `PAGES.md`, `REFS.md`, `DESIGN.md`, planches 01–03 (page Jeu).
