# A07 – Épreuve E6 blanche : expression de besoins, réalisation, recette

## 1. Le déroulement à reproduire

| Temps | Contenu |
|---|---|
| **Préparation 1** : 30 min | Étude de l'expression de besoins |
| **Entretien 1** : 20 min | Présentation de l'analyse, des spécifications, des outils et de la démarche |
| **Préparation 2** : 1 h | Réalisation de la solution en autonomie |
| **Entretien 2** : 20 min | Recette, puis entretien d'explicitation |

Voir aussi [Épreuves E6](../../ressources/epreuves-e5-e6.md). Les rôles : **candidat**, **commission** (un camarade ou l'enseignant), **observateur** (chronomètre et grille).

## 2. L'expression de besoins (cas fictif)

> *L'agence « Cabinet Delmas Conseil » (entreprise fictive, 9 salariés) ouvre un nouveau segment réseau pour ses postes de travail. Besoins exprimés :*
>
> 1. *Un service **DHCP** attribue automatiquement les adresses sur le réseau `192.168.60.0/24`.*
> 2. *La passerelle est `192.168.60.1` ; le serveur est `192.168.60.10`.*
> 3. *Les adresses dynamiques vont de `192.168.60.100` à `192.168.60.199`.*
> 4. *Trois imprimantes reçoivent toujours la même adresse (réservations), à partir de `192.168.60.20`.*
> 5. *La durée du bail est de **8 heures**.*
> 6. *Un service **DNS** interne résout au moins trois noms de l'agence : `serveur`, `imprimante1`, `passerelle`.*
> 7. *Une **procédure d'une page** est remise à l'administrateur.*

<figure class="graphe diagramme">
<svg viewBox="0.00 0.00 611.60 377.60" style="max-width:816px" role="img" aria-label="Schéma" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<g class="graph" transform="scale(1 1) rotate(0) translate(10.8 366.8)">
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M351.5,-356C351.5,-356 276.5,-356 276.5,-356 270.5,-356 264.5,-350 264.5,-344 264.5,-344 264.5,-331 264.5,-331 264.5,-325 270.5,-319 276.5,-319 276.5,-319 351.5,-319 351.5,-319 357.5,-319 363.5,-325 363.5,-331 363.5,-331 363.5,-344 363.5,-344 363.5,-350 357.5,-356 351.5,-356"/>
<text text-anchor="start" x="283.5" y="-334" font-family="Helvetica,sans-Serif" font-size="15.00">Internet</text>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M396.5,-261C396.5,-261 231.5,-261 231.5,-261 225.5,-261 219.5,-255 219.5,-249 219.5,-249 219.5,-219 219.5,-219 219.5,-213 225.5,-207 231.5,-207 231.5,-207 396.5,-207 396.5,-207 402.5,-207 408.5,-213 408.5,-219 408.5,-219 408.5,-249 408.5,-249 408.5,-255 402.5,-261 396.5,-261"/>
<text text-anchor="start" x="238.5" y="-239" font-family="Helvetica,sans-Serif" font-size="15.00">Routeur de l&#39;agence</text>
<text text-anchor="start" x="263" y="-222" font-family="Helvetica,sans-Serif" font-size="15.00">192.168.60.1</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M314,-318.82C314,-305.53 314,-286.87 314,-270.53"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="317.15,-270.24 314,-261.24 310.85,-270.24 317.15,-270.24"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M373,-149C373,-149 255,-149 255,-149 249,-149 243,-143 243,-137 243,-137 243,-124 243,-124 243,-118 249,-112 255,-112 255,-112 373,-112 373,-112 379,-112 385,-118 385,-124 385,-124 385,-137 385,-137 385,-143 379,-149 373,-149"/>
<text text-anchor="start" x="262" y="-127" font-family="Helvetica,sans-Serif" font-size="15.00">Commutateur</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M314,-206.86C314,-192.02 314,-173.48 314,-158.5"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="317.15,-158.24 314,-149.24 310.85,-158.24 317.15,-158.24"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M188,-54C188,-54 12,-54 12,-54 6,-54 0,-48 0,-42 0,-42 0,-12 0,-12 0,-6 6,0 12,0 12,0 188,0 188,0 194,0 200,-6 200,-12 200,-12 200,-42 200,-42 200,-48 194,-54 188,-54"/>
<text text-anchor="start" x="19" y="-32" font-family="Helvetica,sans-Serif" font-size="15.00">Serveur DHCP et DNS</text>
<text text-anchor="start" x="44" y="-15" font-family="Helvetica,sans-Serif" font-size="15.00">192.168.60.10</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M276.72,-111.82C245.44,-96.98 200.07,-75.46 163.14,-57.95"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="164.39,-55.05 154.91,-54.04 161.69,-60.75 164.39,-55.05"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M375.5,-45.5C375.5,-45.5 252.5,-45.5 252.5,-45.5 246.5,-45.5 240.5,-39.5 240.5,-33.5 240.5,-33.5 240.5,-20.5 240.5,-20.5 240.5,-14.5 246.5,-8.5 252.5,-8.5 252.5,-8.5 375.5,-8.5 375.5,-8.5 381.5,-8.5 387.5,-14.5 387.5,-20.5 387.5,-20.5 387.5,-33.5 387.5,-33.5 387.5,-39.5 381.5,-45.5 375.5,-45.5"/>
<text text-anchor="start" x="259.5" y="-23.5" font-family="Helvetica,sans-Serif" font-size="15.00">3 imprimantes</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M314,-111.82C314,-96.2 314,-73.17 314,-55.2"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="317.15,-54.82 314,-45.82 310.85,-54.82 317.15,-54.82"/>
</g>
<g class="node n&#45;rect">
<path fill="none" stroke="black" stroke-width="1.8" d="M578,-45.5C578,-45.5 440,-45.5 440,-45.5 434,-45.5 428,-39.5 428,-33.5 428,-33.5 428,-20.5 428,-20.5 428,-14.5 434,-8.5 440,-8.5 440,-8.5 578,-8.5 578,-8.5 584,-8.5 590,-14.5 590,-20.5 590,-20.5 590,-33.5 590,-33.5 590,-39.5 584,-45.5 578,-45.5"/>
<text text-anchor="start" x="447" y="-23.5" font-family="Helvetica,sans-Serif" font-size="15.00">Postes de travail</text>
</g>
<g class="edge">
<path fill="none" stroke="black" stroke-width="1.8" d="M347.97,-111.82C381,-94.63 431.27,-68.46 466.84,-49.94"/>
<polygon fill="black" stroke="black" stroke-width="1.8" points="468.57,-52.6 475.1,-45.65 465.66,-47.01 468.57,-52.6"/>
</g>
</g>
</svg>
</figure>

## 3. Préparation 1 : analyser (30 minutes)

Méthode en cinq temps :

1. **Souligner** les exigences ;
2. **Lister** l'existant (réseau, adresses) et ce qui manque ;
3. **Traduire** en spécifications techniques ;
4. **Choisir** les outils et justifier ;
5. **Prévoir** les tests de recette.

**Exercice 1.** Calcule : le nombre d'adresses de la plage dynamique, le nombre d'adresses utilisables d'un réseau `/24`, et la durée du bail en secondes.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Plage dynamique : de `.100` à `.199` inclus, soit \(199 - 100 + 1 = 100\) adresses. Réseau `/24` : \(2^8 - 2 = 254\) adresses utilisables. Bail : \(8 \times 3600 = 28\,800\) secondes.

</details>

**Exercice 2.** Écris les **spécifications techniques** correspondant aux sept besoins.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

| Besoin | Spécification |
|---|---|
| 1 | Un serveur DHCP actif sur l'interface du réseau `192.168.60.0/24` |
| 2 | Option passerelle `192.168.60.1` ; adresse fixe du serveur `192.168.60.10` |
| 3 | Étendue dynamique `192.168.60.100` à `192.168.60.199` |
| 4 | Trois réservations par adresse physique (`.20`, `.21`, `.22`) |
| 5 | Durée de bail de 28 800 secondes (8 h) |
| 6 | Zone DNS interne avec trois enregistrements : `serveur` (`.10`), `imprimante1` (`.20`), `passerelle` (`.1`) |
| 7 | Document d'une page : installation, paramètres, tests, restauration |

</details>

## 4. Entretien 1 : présenter son analyse (20 minutes)

Structure conseillée (10 minutes de présentation, 10 minutes de questions) : les besoins, les spécifications, les outils choisis **et pourquoi**, le plan de réalisation avec les durées, les tests de recette.

## 5. Préparation 2 : réaliser en 60 minutes

| Durée | Tâche |
|---|---|
| 5 min | Vérifier l'environnement (adresse du serveur, connectivité) |
| 15 min | Installer et configurer le service DHCP (étendue, option passerelle, bail) |
| 10 min | Réservations des trois imprimantes |
| 10 min | Zone DNS et trois enregistrements |
| 10 min | Tests de recette |
| 10 min | Procédure d'une page |

> [!WARNING]
> **Sauvegarde** : avant de modifier une configuration, copie le fichier d'origine. Tu es responsable de l'usage de l'environnement.

## 6. Entretien 2 : recette et explicitation (20 minutes)

### Tests de recette à dérouler

| N° | Test | Résultat attendu |
|---|---|---|
| 1 | Un poste demande une adresse | Adresse entre `.100` et `.199`, passerelle `.1` |
| 2 | Vérifier la durée du bail | 8 heures |
| 3 | Une imprimante demande une adresse | Toujours la même (`.20`, `.21` ou `.22`) |
| 4 | Résoudre `serveur` | `192.168.60.10` |
| 5 | Résoudre `passerelle` | `192.168.60.1` |
| 6 | Redémarrer le service | Les paramètres sont conservés |

L'entretien d'explicitation porte sur la **conformité**, l'**opérationnalité**, la **pertinence des outils** et la **démarche**.

## 7. Grille d'observation

| Critère | Observé |
|---|---|
| Exigences correctement identifiées |  |
| Spécifications cohérentes et complètes |  |
| Plan de réalisation chiffré en temps |  |
| Solution réalisée dans l'heure |  |
| Tests de recette déroulés et notés |  |
| Choix techniques justifiés |  |
| Procédure remise |  |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Analyse : exigences et spécifications | 5 |  |
| Plan de réalisation chiffré | 3 |  |
| Réalisation conforme dans l'heure | 5 |  |
| Recette : tests prévus et déroulés | 4 |  |
| Explicitation des choix et de la démarche | 3 |  |
| **Total** | **20** |  |
