# B03 – Conduire et clore le projet de fin d'année

## 1. Cadrer

| Élément | Question | Exemple (fictif) |
|---|---|---|
| **Objectif** | Que veut-on obtenir, mesurable ? | Migrer 12 postes vers la nouvelle version du système avant le 15 juin |
| **Périmètre** | Ce qui est inclus et exclu | Postes de bureau inclus ; serveurs exclus |
| **Livrables** | Ce qui sera remis | Postes migrés, procédure, bilan |
| **Acteurs** | Qui fait quoi | Chef de projet, technicien, utilisateurs pilotes |
| **Contraintes** | Délai, budget, disponibilité | Migration hors heures de bureau |

## 2. Planning et chemin critique

On liste les **tâches**, leur **durée** et leurs **dépendances**.

| Tâche | Durée (jours) | Dépend de |
|---|---:|---|
| A. Préparer l'image de poste | 2 | - |
| B. Migrer le groupe 1 | 3 | A |
| C. Former les utilisateurs | 2 | A |
| D. Recette et bilan | 1 | B et C |

<figure class="graphe diagramme">
<svg viewBox="0.00 0.00 493.10 299.60" style="max-width:657px" role="img" aria-label="Schéma" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<g class="graph" transform="scale(1 1) rotate(0) translate(10.8 288.8)">
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M309.5,-278C309.5,-278 147.5,-278 147.5,-278 141.5,-278 135.5,-272 135.5,-266 135.5,-266 135.5,-236 135.5,-236 135.5,-230 141.5,-224 147.5,-224 147.5,-224 309.5,-224 309.5,-224 315.5,-224 321.5,-230 321.5,-236 321.5,-236 321.5,-266 321.5,-266 321.5,-272 315.5,-278 309.5,-278"/>
<text text-anchor="start" x="154.5" y="-256" font-family="Helvetica,sans-Serif" font-size="15.00">A : Préparer l&#39;image</text>
<text text-anchor="start" x="202.5" y="-239" font-family="Helvetica,sans-Serif" font-size="15.00">2 jours</text>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M189,-166C189,-166 12,-166 12,-166 6,-166 0,-160 0,-154 0,-154 0,-124 0,-124 0,-118 6,-112 12,-112 12,-112 189,-112 189,-112 195,-112 201,-118 201,-124 201,-124 201,-154 201,-154 201,-160 195,-166 189,-166"/>
<text text-anchor="start" x="19" y="-144" font-family="Helvetica,sans-Serif" font-size="15.00">B : Migrer le groupe 1</text>
<text text-anchor="start" x="74.5" y="-127" font-family="Helvetica,sans-Serif" font-size="15.00">3 jours</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M198.17,-223.93C180.12,-208.43 157.09,-188.64 137.93,-172.17"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="139.94,-169.74 131.06,-166.26 135.83,-174.52 139.94,-169.74"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M459.5,-166C459.5,-166 253.5,-166 253.5,-166 247.5,-166 241.5,-160 241.5,-154 241.5,-154 241.5,-124 241.5,-124 241.5,-118 247.5,-112 253.5,-112 253.5,-112 459.5,-112 459.5,-112 465.5,-112 471.5,-118 471.5,-124 471.5,-124 471.5,-154 471.5,-154 471.5,-160 465.5,-166 459.5,-166"/>
<text text-anchor="start" x="260.5" y="-144" font-family="Helvetica,sans-Serif" font-size="15.00">C : Former les utilisateurs</text>
<text text-anchor="start" x="330.5" y="-127" font-family="Helvetica,sans-Serif" font-size="15.00">2 jours</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M258.83,-223.93C276.88,-208.43 299.91,-188.64 319.07,-172.17"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="321.17,-174.52 325.94,-166.26 317.06,-169.74 321.17,-174.52"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M308,-54C308,-54 149,-54 149,-54 143,-54 137,-48 137,-42 137,-42 137,-12 137,-12 137,-6 143,0 149,0 149,0 308,0 308,0 314,0 320,-6 320,-12 320,-12 320,-42 320,-42 320,-48 314,-54 308,-54"/>
<text text-anchor="start" x="156" y="-32" font-family="Helvetica,sans-Serif" font-size="15.00">D : Recette et bilan</text>
<text text-anchor="start" x="206.5" y="-15" font-family="Helvetica,sans-Serif" font-size="15.00">1 jour</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M130.83,-111.93C148.88,-96.43 171.91,-76.64 191.07,-60.17"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="193.17,-62.52 197.94,-54.26 189.06,-57.74 193.17,-62.52"/>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M326.17,-111.93C308.12,-96.43 285.09,-76.64 265.93,-60.17"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="267.94,-57.74 259.06,-54.26 263.83,-62.52 267.94,-57.74"/>
</g>
</g>
</svg>
</figure>

Le **chemin critique** est le chemin le plus long : c'est lui qui fixe la durée du projet.

| Chemin | Durée |
|---|---:|
| A, B, D | \(2 + 3 + 1 = 6\) jours |
| A, C, D | \(2 + 2 + 1 = 5\) jours |

Durée minimale du projet : **6 jours** ; chemin critique : **A, B, D**. La tâche C a **1 jour de marge** : elle peut prendre 3 jours sans retarder le projet.

**Exercice 1.** On ajoute la tâche E « Sauvegarder les données des postes » (2 jours) qui dépend de A et dont dépend B. Quelle est la nouvelle durée minimale ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Chemins : A, E, B, D = \(2 + 2 + 3 + 1 = 8\) jours ; A, C, D = 5 jours. Durée minimale : **8 jours**, chemin critique **A, E, B, D**.

</details>

## 3. Les risques

On note chaque risque par **probabilité** (1 faible, 3 forte) et **impact** (1 faible, 3 fort). La **criticité** est leur produit.

| Risque | P | I | Criticité | Action |
|---|---:|---:|---:|---|
| Image de poste défaillante | 2 | 3 | 6 | Test sur un poste pilote avant le groupe 1 |
| Utilisateurs indisponibles pour la formation | 3 | 1 | 3 | Prévoir deux créneaux |
| Perte de données lors de la migration | 1 | 3 | 3 | Sauvegarde préalable (tâche E) |

**Exercice 2.** Quel risque traiter en premier ? Quelle criticité maximale possible avec ces échelles ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Le risque de criticité **6** (image de poste défaillante). Criticité maximale : \(3 \times 3 = 9\).

</details>

## 4. Suivre l'avancement

| Tâche | Prévu | Réalisé | Écart |
|---|---:|---:|---:|
| A | 2 | 2 | 0 |
| B | 3 | 4 | +1 |
| C | 2 | 2 | 0 |
| D | 1 | 1 | 0 |

Somme des durées : 8 jours prévus, 9 réalisés (la somme des durées n'est pas la durée du projet, qui dépend du chemin critique). La tâche B a pris 1 jour de plus, donc la date de fin recule d'un jour. Un écart se note **avec sa cause** et son effet sur la date de fin.

## 5. Clôturer : le bilan

| Rubrique | Contenu |
|---|---|
| Objectif atteint ? | Oui / en partie / non, avec preuve (tests, recette) |
| Planning | Écart total et cause |
| Risques | Ceux qui sont arrivés, ceux évités |
| **Retour d'expérience** | Ce que je garde, ce que je changerais |
| Livrables remis | Liste |

> [!TIP]
> Dans l'oral, un projet qui a dérapé **et dont tu expliques la cause** vaut mieux qu'un projet « sans problème » que tu ne sais pas détailler.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Cadrage : objectif mesurable et périmètre | 4 |  |
| Planning avec dépendances et chemin critique | 6 |  |
| Risques notés et traités | 4 |  |
| Suivi prévu / réalisé | 3 |  |
| Bilan et retour d'expérience | 3 |  |
| **Total** | **20** |  |
