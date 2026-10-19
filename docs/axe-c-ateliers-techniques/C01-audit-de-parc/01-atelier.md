# C01 – Auditer un parc et planifier la remédiation

## 1. Auditer, c'est comparer à un référentiel

Un audit compare **ce qui existe** à **ce qui devrait exister**. Sans référentiel, on ne peut pas parler d'écart.

| Critère du référentiel (exemple) | Vérifiable comment ? |
|---|---|
| Système à jour des correctifs | Version et date de dernière mise à jour |
| Antivirus actif | État du service |
| Disque chiffré | État du chiffrement |
| Compte administrateur local désactivé | Liste des comptes |
| Poste inventorié | Présence dans l'inventaire |

## 2. Relevé des écarts (parc fictif de 20 postes)

| Critère | Postes conformes | Postes non conformes |
|---|---:|---:|
| Correctifs à jour | 15 | 5 |
| Antivirus actif | 19 | 1 |
| Disque chiffré | 8 | 12 |
| Admin local désactivé | 20 | 0 |

**Taux de conformité** d'un critère = postes conformes ÷ postes total.

**Exercice 1.** Calcule le taux de chaque critère.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Correctifs : \(15/20 = 75\ \%\). Antivirus : \(19/20 = 95\ \%\). Chiffrement : \(8/20 = 40\ \%\). Admin local : \(20/20 = 100\ \%\).

</details>

## 3. Prioriser

Note chaque écart : **probabilité** d'exploitation (1 à 3) × **impact** (1 à 3).

| Écart | P | I | Criticité |
|---|---:|---:|---:|
| Disques non chiffrés (12 postes, portables en déplacement) | 2 | 3 | 6 |
| Correctifs manquants (5 postes) | 3 | 3 | 9 |
| Antivirus inactif (1 poste) | 2 | 3 | 6 |

**Exercice 2.** Quel écart traiter en premier ? Quel écart, malgré une criticité moindre, concerne le plus de postes ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

Premier : les **correctifs** (criticité 9). Le plus de postes : le **chiffrement** (12 postes sur 20), à planifier dans un lot dédié.

</details>

## 4. Plan de remédiation

| Action | Responsable | Échéance | Preuve de fin |
|---|---|---|---|
| Appliquer les correctifs sur 5 postes | Technicien | Semaine 1 | Liste des versions |
| Réactiver l'antivirus du poste concerné | Technicien | Semaine 1 | Capture de l'état |
| Chiffrer les 12 disques, 4 par semaine | Technicien | Semaines 2 à 4 | Rapport de chiffrement |
| Contrôle final | Responsable | Semaine 5 | Nouveau relevé |

Chiffrement : \(12 / 4 = 3\) semaines.

> [!NOTE]
> Un plan sans **preuve de fin** ne se contrôle pas. Le contrôle final refait le relevé et doit montrer des taux de 100 %.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Référentiel vérifiable | 4 |  |
| Relevé et taux corrects | 5 |  |
| Priorisation justifiée | 4 |  |
| Plan avec échéances et preuves | 5 |  |
| Restitution claire | 2 |  |
| **Total** | **20** |  |
