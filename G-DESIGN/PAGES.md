# PAGES — Écho

> Proposé le 2026-11-18 (V1). Les 4 pages sont validées par Gaia le 2026-11-18 (V3). Les questions [H] restent ouvertes.
> Source : `IDEE.md` (pitch, mécanique, boucle quotidienne, carte de fin) + critères Stage 2.
> Planches en desktop seul, 1440 × 900 (décision de Gaia du 2026-11-18 : le règlement du hackathon n'exige pas le mobile).

| # | Page | Rôle | Contenu clé | Statut |
|---|------|------|-------------|--------|
| 1 | **Post** | Ce qu'on voit en scrollant le feed, avant d'interagir. Doit donner envie de taper en 5 secondes. | En-tête du post (communauté, titre du jour), aperçu de la salle du jour au repos, numéro de salle + date, nombre de joueurs du jour, un seul appel à l'action (« Start listening »). | **validée** — `planches/v3/02-post.html` |
| 2 | **Jeu** *(page principale)* | L'écran où l'on joue. Une seule règle : on tape pour émettre, le retard de l'écho donne la distance, on recoupe. | Salle du jour, pings émis et leurs anneaux de distance, onde en cours, relevés (retard ms → distance m), pings restants, série, action « Mark the object ». | **validée** — `planches/v3/01-sable.html` (style de référence, voir `STYLE.md`) |
| 3 | **Carte de fin** | Clore la partie du jour et donner une raison de commenter. | Résultat (trouvé / écart en m, pings utilisés), série mise à jour, comparaison à la communauté du jour, bouton « Comment your result » (un tap), compte à rebours vers la prochaine salle. | **validée** — `planches/v3/03-fin.html` |
| 4 | **Séries & classement** | Le versant communautaire : revenir demain, se comparer aujourd'hui. | Série perso (jours consécutifs, record), distribution des scores du jour, classement du jour, historique des 7 dernières salles. | **validée** — `planches/v3/04-series.html` |

## Questions produit ouvertes (non tranchées par `IDEE.md`)

Les planches utilisent des hypothèses marquées **[H]**. Elles ne sont pas des décisions :

1. **[H] Budget de pings** — 5 pings par salle. Combien, et le score dépend-il du nombre de pings, de l'écart au marqueur, ou des deux ?
2. **[H] Forme de la salle** — carré de 10 × 10 m vu de dessus. Une seule forme fixe, ou variable selon le seed ?
3. **[H] Fin de partie** — le joueur pose un marqueur (« Mark the object ») ; un seul essai ?
4. **[H] Ce qu'on « trouve »** — un objet sans nom ni silhouette. Faut-il nommer l'objet du jour (ex. révélé sur la carte de fin) ?
5. **Classement** — public par pseudo, ou seulement des agrégats (médiane, distribution) ?
6. **Son** — `IDEE.md` mentionne des sons embarqués : l'écho est-il aussi audible (indice sonore) ou seulement visuel ?
7. **[H] Commentaire en un tap** — la carte de fin propose de poster une ligne sans spoiler : `écho 014 · ●●●●○ · 0.42 m` (pings utilisés, pings restants, écart). Format à valider.
8. **[H] Définition de la série** — jours joués consécutifs (une salle ratée compte quand même).
9. **[H] Rang** — affiché en pourcentage sur la carte de fin (« Better than 62 % »), en rang absolu dans le classement ; tri par pings puis par écart.
