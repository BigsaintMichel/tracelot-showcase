# TraceLot / BioStock

**Solution de traçabilité et de sécurisation de la chaîne d'approvisionnement en biomasse**

Projet ECOR Divo — SODEN, Côte d'Ivoire

---

## Le projet en une phrase

Une solution logicielle complète qui trace chaque lot de biomasse du village producteur jusqu'à la chaudière de la centrale thermique, détecte les fraudes automatiquement et fournit des preuves infalsifiables via blockchain.

---

## Le problème

La centrale thermique ECOR Divo (76 MW, 600 000 tonnes de biomasse par an) doit s'approvisionner auprès de **36 000 producteurs** répartis dans les villages de la région du Lôh-Djiboua.

Entre la collecte et la chaudière, trois dérives sont possibles :

1. **Mouillage frauduleux** — ajout d'eau dans les sacs pour gonfler le poids facturé
2. **Vol de matière** — disparition de sacs en cours de transport
3. **Erreurs de mesure** — balances mal calibrées, saisies approximatives

**Résultat :** la centrale paie pour de l'eau, reçoit un combustible de qualité variable, et n'a aucune preuve en cas de litige.

---

## La solution

Deux applications complémentaires :

| Application | Support | Rôle |
|---|---|---|
| **TraceLot** | Mobile Android | Capture terrain (collecte, logistique, réception) |
| **BioStock** | Web | Supervision usine (analyse, alertes, décisions) |

Un backend Node.js central calcule la matière sèche réelle, détecte les fraudes, et déclenche l'ancrage blockchain.

---

## Fonctionnalités clés

### TraceLot mobile
- Création de lot avec tag QR unique
- Enregistrement poids, humidité, GPS
- Scan continu des sacs au chargement
- Réception au pont-bascule avec calcul MS en temps réel
- **Fonctionne sans réseau** (offline-first)
- Détection automatique du double scan

### BioStock web
- Tableau de bord temps réel
- Vue réconciliation MS₁ vs MS₂
- Traitement des alertes
- Analyse des tendances par village / agent / transporteur
- Suivi du stock par type de biomasse

### Moteur anti-fraude
- Calcul automatique de la matière sèche
- 5 niveaux de verdict : CONFORME / ALERTE HUMIDITÉ / ALERTE PERTE MS / ANOMALIE BALANCE / ALERTE COMBINÉE
- Détection du mouillage et du vol
- Ancrage blockchain SHA-256 sur Hedera

---

## Architecture
