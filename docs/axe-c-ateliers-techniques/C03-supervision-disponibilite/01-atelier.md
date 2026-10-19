# C03 – Superviser et calculer la disponibilité

## 1. Que surveiller ?

| Niveau | Indicateur | Exemple |
|---|---|---|
| Machine | Occupation disque, mémoire, processeur | Disque à 82 % |
| Service | Service démarré, port ouvert | Service web répond |
| Utilisateur | Temps de réponse, page testée | Page d'accueil en moins de 2 s |

## 2. Deux seuils

| Seuil | Signification | Réaction |
|---|---|---|
| **Avertissement** | À traiter bientôt | Ticket, pas de réveil |
| **Critique** | Service en danger | Alerte immédiate |

Exemple : disque de 500 Go, avertissement à 80 %, critique à 90 %.

**Exercice 1.** Avec 410 Go utilisés, dans quel état est le disque ? À partir de combien de Go l'alerte critique ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

\(410/500 = 82\ \%\) : **avertissement**. Critique à \(0{,}90 \times 500 = 450\) Go.

</details>

> [!TIP]
> Trop d'alertes inutiles font ignorer les vraies : n'alerte que si une action est attendue.

## 3. La disponibilité

\[ \text{Disponibilité} = \frac{\text{temps total} - \text{temps d'indisponibilité}}{\text{temps total}} \]

Sur un mois de 30 jours : \(30 \times 24 \times 60 = 43\,200\) minutes.

**Exercice 2.** Un service est indisponible 45 minutes dans le mois. Quelle disponibilité ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

\((43\,200 - 45)/43\,200 \approx 0{,}99896\), soit **99,90 %** arrondi à deux décimales (99,896 % sans arrondir).

</details>

**Exercice 3.** Combien de minutes d'indisponibilité tolère-t-on par mois à 99 %, 99,5 % et 99,9 % ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

| Objectif | Indisponibilité tolérée par mois de 30 jours |
|---|---:|
| 99 % | 432 min (7 h 12) |
| 99,5 % | 216 min (3 h 36) |
| 99,9 % | 43,2 min |

Le cas de 45 minutes **dépasse** donc l'objectif de 99,9 %.

</details>

## 4. La fiche de supervision

| Indicateur | Seuil avertissement | Seuil critique | Action attendue | Qui est alerté |
|---|---|---|---|---|
| Occupation disque | 80 % | 90 % | Libérer ou agrandir | Technicien |
| Service web répond | - | 2 échecs successifs | Redémarrer, diagnostiquer | Technicien |
| Temps de réponse | 2 s | 5 s | Chercher la charge | Technicien |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Indicateurs pertinents | 4 |  |
| Deux seuils cohérents | 4 |  |
| Calculs de disponibilité corrects | 6 |  |
| Actions et destinataires | 4 |  |
| Pas d'alerte inutile | 2 |  |
| **Total** | **20** |  |
