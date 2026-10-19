# C02 – Gérer un incident et rédiger le retour d'expérience

## 1. Le cycle d'un incident

<figure class="graphe diagramme">
<svg viewBox="0.00 0.00 210.60 438.60" style="max-width:281px" role="img" aria-label="Schéma" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<g class="graph" transform="scale(1 1) rotate(0) translate(10.8 427.8)">
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M138,-417C138,-417 51,-417 51,-417 45,-417 39,-411 39,-405 39,-405 39,-392 39,-392 39,-386 45,-380 51,-380 51,-380 138,-380 138,-380 144,-380 150,-386 150,-392 150,-392 150,-405 150,-405 150,-411 144,-417 138,-417"/>
<text text-anchor="start" x="58" y="-395" font-family="Helvetica,sans-Serif" font-size="15.00">Détection</text>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M150,-322C150,-322 39,-322 39,-322 33,-322 27,-316 27,-310 27,-310 27,-297 27,-297 27,-291 33,-285 39,-285 39,-285 150,-285 150,-285 156,-285 162,-291 162,-297 162,-297 162,-310 162,-310 162,-316 156,-322 150,-322"/>
<text text-anchor="start" x="46" y="-300" font-family="Helvetica,sans-Serif" font-size="15.00">Qualification</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M94.5,-379.57C94.5,-365.84 94.5,-346.7 94.5,-331.18"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="97.65,-331.06 94.5,-322.06 91.35,-331.06 97.65,-331.06"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M141,-227C141,-227 48,-227 48,-227 42,-227 36,-221 36,-215 36,-215 36,-202 36,-202 36,-196 42,-190 48,-190 48,-190 141,-190 141,-190 147,-190 153,-196 153,-202 153,-202 153,-215 153,-215 153,-221 147,-227 141,-227"/>
<text text-anchor="start" x="55" y="-205" font-family="Helvetica,sans-Serif" font-size="15.00">Résolution</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M94.5,-284.57C94.5,-270.84 94.5,-251.7 94.5,-236.18"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="97.65,-236.06 94.5,-227.06 91.35,-236.06 97.65,-236.06"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M129,-132C129,-132 60,-132 60,-132 54,-132 48,-126 48,-120 48,-120 48,-107 48,-107 48,-101 54,-95 60,-95 60,-95 129,-95 129,-95 135,-95 141,-101 141,-107 141,-107 141,-120 141,-120 141,-126 135,-132 129,-132"/>
<text text-anchor="start" x="67" y="-110" font-family="Helvetica,sans-Serif" font-size="15.00">Clôture</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M94.5,-189.57C94.5,-175.84 94.5,-156.7 94.5,-141.18"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="97.65,-141.06 94.5,-132.06 91.35,-141.06 97.65,-141.06"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M177,-37C177,-37 12,-37 12,-37 6,-37 0,-31 0,-25 0,-25 0,-12 0,-12 0,-6 6,0 12,0 12,0 177,0 177,0 183,0 189,-6 189,-12 189,-12 189,-25 189,-25 189,-31 183,-37 177,-37"/>
<text text-anchor="start" x="19" y="-15" font-family="Helvetica,sans-Serif" font-size="15.00">Retour d&#39;expérience</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M94.5,-94.57C94.5,-80.84 94.5,-61.7 94.5,-46.18"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="97.65,-46.06 94.5,-37.06 91.35,-46.06 97.65,-46.06"/>
</g>
</g>
</svg>
</figure>

## 2. Chronologie (cas fictif)

| Heure | Événement |
|---|---|
| 14 h 05 | Un utilisateur signale que l'application de gestion ne s'ouvre plus |
| 14 h 20 | Incident qualifié : base de données arrêtée |
| 14 h 40 | Cause trouvée : disque plein sur le serveur |
| 15 h 20 | Espace libéré, base redémarrée |
| 15 h 35 | Utilisateurs confirment le retour du service |

**Exercice 1.** Calcule la durée de l'incident (signalement à retour confirmé), le temps de qualification et le temps de résolution (de la qualification au retour).

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Durée totale : 14 h 05 à 15 h 35 = **90 min**. Qualification : 14 h 05 à 14 h 20 = **15 min**. Résolution : 14 h 20 à 15 h 35 = **75 min**. Contrôle : \(15 + 75 = 90\).

</details>

## 3. La cause racine : cinq pourquoi

1. Pourquoi l'application ne s'ouvre-t-elle plus ? La base est arrêtée.
2. Pourquoi ? Elle ne pouvait plus écrire.
3. Pourquoi ? Le disque était plein.
4. Pourquoi ? Les journaux n'étaient pas purgés.
5. Pourquoi ? Aucune tâche de purge ni alerte d'espace disque.

**Cause racine** : absence de purge et de supervision de l'espace disque, pas « la base qui plante ».

> [!WARNING]
> Un REX cherche un **défaut de processus**, jamais un coupable.

## 4. Le retour d'expérience

| Rubrique | Contenu |
|---|---|
| Résumé | Une phrase |
| Impact | 90 min, utilisateurs touchés |
| Chronologie | Tableau ci-dessus |
| Cause racine | Absence de purge et d'alerte |
| Ce qui a bien marché | Qualification rapide |
| Ce qui a mal marché | Détection par l'utilisateur, pas par une alerte |
| **Actions** | Purge hebdomadaire ; alerte à 80 % ; vérification dans la liste de contrôle mensuelle |

**Exercice 2.** Rédige deux actions préventives **mesurables** pour ce REX.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

« Mettre en place d'ici fin du mois une purge hebdomadaire des journaux, vérifiée dans le rapport hebdomadaire. » « Configurer une alerte d'avertissement à 80 % d'occupation du disque du serveur et tester qu'elle déclenche un message. »

</details>

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Chronologie datée et claire | 4 |  |
| Durées correctes | 4 |  |
| Cause racine par les cinq pourquoi | 5 |  |
| Actions mesurables | 5 |  |
| Ton sans coupable | 2 |  |
| **Total** | **20** |  |
