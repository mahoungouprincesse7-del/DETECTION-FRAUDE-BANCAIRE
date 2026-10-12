# Détection de fraude bancaire — Machine Learning

Projet de classification supervisée réalisé avec **Python** et **scikit-learn** pour repérer des transactions frauduleuses dans un jeu de données très déséquilibré.

## Données et objectif

- Jeu de données **Credit Card Fraud Detection** (ULB / Worldline), disponible sur Kaggle.
- **284 807 transactions**, dont **492 fraudes** (environ **0,173 %**).
- Objectif : détecter les fraudes tout en surveillant les faux positifs.

## Démarche

1. Exploration des données, distribution des classes et corrélations.
2. Préparation des variables et standardisation du montant.
3. Séparation entraînement/test **80/20 avec stratification**.
4. Comparaison de la **régression logistique** et d'un **Random Forest** (200 arbres).
5. Évaluation avec précision, rappel, F1-score, matrice de confusion et courbe ROC/AUC.

## Résultats du notebook

Sur l'ensemble de test, le **Random Forest** obtient, pour la classe fraude :

| Indicateur | Valeur |
|---|---:|
| Précision | 0,94 |
| Rappel | 0,81 |
| F1-score | 0,87 |
| AUC-ROC | 0,9704 |

Ces scores correspondent à l'exécution enregistrée dans le notebook ; ils peuvent varier en cas de modification du jeu de données ou du pipeline. L'accuracy seule est peu informative face au fort déséquilibre des classes.

## Consulter et reproduire

Le projet se trouve dans [`notebook1c3d55121c (1).ipynb`](notebook1c3d55121c%20(1).ipynb).

Pour reproduire **tel quel** le notebook, l'ouvrir dans **Kaggle Notebooks** et ajouter le jeu de données `mlg-ulb/creditcardfraud`, car le chargement du CSV utilise un chemin `/kaggle/input/...`. En local, télécharger `creditcard.csv` et adapter ce chemin.

Bibliothèques principales : `pandas`, `numpy`, `matplotlib`, `seaborn` et `scikit-learn`.

**Piste d'amélioration technique :** intégrer la standardisation dans un pipeline ajusté uniquement sur les données d'entraînement, puis recalculer les métriques pour éviter toute fuite d'information lors de la préparation des données.
