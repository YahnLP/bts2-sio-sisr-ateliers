# B04 – Communication de crise : informer sans paniquer

## 1. Pourquoi communiquer pendant l'incident

Pendant un incident, les utilisateurs veulent **savoir** : est-ce que ça touche moi, que dois-je faire, quand sera-ce réglé ? Un silence fait **monter les appels** (chacun appelle pour demander) et **baisse la confiance**.

## 2. Les trois messages

| Message | Quand | Contenu |
|---|---|---|
| **Alerte** | Dès que l'incident est confirmé | Ce qui ne marche pas, qui est touché, ce qu'il faut faire en attendant, **heure du prochain message** |
| **Point d'étape** | À l'heure annoncée, même sans nouveauté | Où on en est, nouvelle estimation, ce qui reste à faire |
| **Clôture** | Service rétabli | Ce qui est rétabli, la cause **en une phrase**, ce qu'il faut faire (si besoin), remerciements |

## 3. Public et ton

| Public | Ce qu'il veut | Ton |
|---|---|---|
| **Utilisateurs** | Savoir ce qu'ils peuvent faire | Court, sans jargon, actionnable |
| **Direction** | Impact sur l'activité, durée, décision à prendre | Chiffré, factuel |
| **Équipe technique** | Détails techniques | Précis |

## 4. Exercice : réécrire un mauvais message

> *Message fictif envoyé à tous les salariés : « Bonjour, il y a un souci avec l'infrastructure, on regarde. Merci de votre patience. »*

**Questions** : quels sont les défauts ? Réécris le message pour l'incident suivant (fictif) : *la messagerie est inaccessible depuis 9 h 10 ; seuls les envois sont touchés, la réception fonctionne ; le technicien a identifié un service arrêté sur le serveur de messagerie ; un point sera fait à 10 h.*

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**Défauts** : « souci » et « infrastructure » sont flous ; aucun service précisé ; aucune consigne ; aucune heure de prochain message ; aucune estimation.

**Réécriture** : « Objet : Messagerie : envoi de courriels indisponible. Depuis 9 h 10, l'envoi de courriels est impossible ; la réception fonctionne. Nous avons identifié un service arrêté sur le serveur de messagerie et travaillons à le rétablir. En attendant, vous pouvez préparer vos messages et les envoyer plus tard ; pour une urgence, appelez le correspondant concerné. Prochaine information à 10 h. »

</details>

## 5. Série complète pour un incident fictif

> *Incident : la messagerie est inaccessible de 9 h 10 à 11 h 40. La cause : un disque plein sur le serveur de messagerie. Le point d'étape a eu lieu à 10 h.*

**Questions**

1. Combien de temps a duré l'incident ?
2. Rédige le **point d'étape de 10 h** (la cause est identifiée, la libération d'espace est en cours, rétablissement estimé avant midi).
3. Rédige le **message de clôture de 11 h 40**.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**1.** De 9 h 10 à 11 h 40 : 2 h 30, soit **150 minutes**.

**2.** « Point de 10 h : la cause est identifiée, c'est un disque saturé sur le serveur de messagerie. Nous libérons de l'espace. Rétablissement estimé avant midi. Prochain point à 11 h. »

**3.** « Clôture : la messagerie fonctionne à nouveau depuis 11 h 40. Cause : un disque saturé sur le serveur ; l'espace a été libéré et une alerte sur l'espace disque sera ajoutée. Les messages en attente partent automatiquement ; aucun message n'est perdu. Merci de votre patience. »

</details>

## 6. Les erreurs à éviter

| Erreur | Effet |
|---|---|
| Promettre une heure sans fondement | Perte de confiance si elle n'est pas tenue |
| Jargon (« le service DNS est KO ») | Incompréhension |
| Accuser une personne | Climat dégradé |
| Se taire jusqu'à la résolution | Appels en cascade |
| Message trop long | Pas lu |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Premier message court et actionnable | 5 |  |
| Heure du prochain message annoncée | 3 |  |
| Public adapté (utilisateurs, direction) | 4 |  |
| Message de clôture complet | 5 |  |
| Calculs et exercices corrects | 3 |  |
| **Total** | **20** |  |
