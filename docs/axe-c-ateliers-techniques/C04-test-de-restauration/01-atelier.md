# C04 – Tester une restauration : RPO, RTO et rapport

## 1. Deux objectifs

| Sigle | Question | Exemple |
|---|---|---|
| **RPO** | Combien de données peut-on perdre ? | 24 h |
| **RTO** | Combien de temps peut durer l'arrêt ? | 1 h |

> [!NOTE]
> Une sauvegarde qui n'a jamais été **restaurée** n'est pas une garantie.

## 2. Vérifier le RPO

Sauvegarde complète chaque nuit à 2 h. Panne à 14 h le même jour.

**Exercice 1.** Quelle durée de données est perdue au plus ? Le RPO de 24 h est-il tenu ? Et si la panne a lieu à 1 h 59 ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Panne à 14 h : \(14 - 2 = 12\) h de données perdues, **RPO tenu**. À 1 h 59 : la dernière sauvegarde date de la veille à 2 h, soit presque 24 h : RPO tenu **de justesse** (23 h 59).

</details>

## 3. Estimer le RTO

Volume : 120 Go. Débit de restauration mesuré : 100 Mo/s. En unités décimales, \(120\,000\) Mo.

<figure class="graphe diagramme">
<svg viewBox="0.00 0.00 225.60 299.60" style="max-width:301px" role="img" aria-label="Schéma" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<g class="graph" transform="scale(1 1) rotate(0) translate(10.8 288.8)">
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M192,-278C192,-278 12,-278 12,-278 6,-278 0,-272 0,-266 0,-266 0,-236 0,-236 0,-230 6,-224 12,-224 12,-224 192,-224 192,-224 198,-224 204,-230 204,-236 204,-236 204,-266 204,-266 204,-272 198,-278 192,-278"/>
<text text-anchor="start" x="19" y="-256" font-family="Helvetica,sans-Serif" font-size="15.00">Restaurer les données</text>
<text text-anchor="start" x="75.5" y="-239" font-family="Helvetica,sans-Serif" font-size="15.00">20 min</text>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M174.5,-166C174.5,-166 29.5,-166 29.5,-166 23.5,-166 17.5,-160 17.5,-154 17.5,-154 17.5,-124 17.5,-124 17.5,-118 23.5,-112 29.5,-112 29.5,-112 174.5,-112 174.5,-112 180.5,-112 186.5,-118 186.5,-124 186.5,-124 186.5,-154 186.5,-154 186.5,-160 180.5,-166 174.5,-166"/>
<text text-anchor="start" x="36.5" y="-144" font-family="Helvetica,sans-Serif" font-size="15.00">Vérifier l&#39;intégrité</text>
<text text-anchor="start" x="75.5" y="-127" font-family="Helvetica,sans-Serif" font-size="15.00">15 min</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M102,-223.93C102,-209.52 102,-191.39 102,-175.68"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="105.15,-175.26 102,-166.26 98.85,-175.26 105.15,-175.26"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M191,-54C191,-54 13,-54 13,-54 7,-54 1,-48 1,-42 1,-42 1,-12 1,-12 1,-6 7,0 13,0 13,0 191,0 191,0 197,0 203,-6 203,-12 203,-12 203,-42 203,-42 203,-48 197,-54 191,-54"/>
<text text-anchor="start" x="20" y="-32" font-family="Helvetica,sans-Serif" font-size="15.00">Redémarrer le service</text>
<text text-anchor="start" x="75.5" y="-15" font-family="Helvetica,sans-Serif" font-size="15.00">10 min</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M102,-111.93C102,-97.52 102,-79.39 102,-63.68"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="105.15,-63.26 102,-54.26 98.85,-63.26 105.15,-63.26"/>
</g>
</g>
</svg>
</figure>

**Exercice 2.** Calcule la durée de restauration des données, puis la durée totale. Le RTO de 1 h est-il tenu ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

\(120\,000 / 100 = 1\,200\) s = **20 min**. Total : \(20 + 15 + 10 = 45\) min, **inférieur à 60 min** : RTO tenu avec 15 min de marge.

</details>

## 4. Le rapport de test

| Rubrique | Contenu |
|---|---|
| Date et périmètre | Serveur de fichiers, sauvegarde de la nuit |
| Objectifs | RPO 24 h ; RTO 1 h |
| Méthode | Restauration sur une machine isolée |
| Mesures | Restauration 20 min ; vérification 15 min ; redémarrage 10 min |
| Constat | Total 45 min ; RTO tenu |
| Problèmes rencontrés | Ex. : mot de passe de la sauvegarde introuvable |
| Actions | Stocker le mot de passe dans le coffre ; refaire le test dans 3 mois |

> [!WARNING]
> Un test réussi **sur un seul fichier** ne prouve pas qu'on peut restaurer **tout le service**.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| RPO et RTO distingués | 4 |  |
| Calculs corrects | 5 |  |
| Test déroulé sur environnement isolé | 4 |  |
| Rapport complet | 5 |  |
| Actions et date du prochain test | 2 |  |
| **Total** | **20** |  |
