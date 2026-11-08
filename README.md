# Air Quality Analytics — Analyse et prédiction du NO₂ à Milan

Projet de Data Analytics, Business Intelligence et Machine Learning réalisé à partir du jeu de données **Air Quality** de l'UCI Machine Learning Repository.

## Objectif
Explorer les concentrations de polluants atmosphériques à Milan, étudier leurs variations temporelles et saisonnières, puis construire un modèle de régression linéaire pour estimer la concentration de NO₂ à partir des mesures disponibles.

## Contenu du dépôt

- `data/` : jeu de données initial et versions préparées.
- `notebooks/01_nettoyage_et_analyse_exploratoire.ipynb` : préparation, traitement des valeurs manquantes, détection des valeurs aberrantes et analyse exploratoire.
- `notebooks/02_prediction_no2_regression_lineaire.ipynb` : préparation des variables, entraînement et évaluation du modèle de régression linéaire.
- `results/` : comparaison des valeurs réelles et prédites, performances et coefficients du modèle.
- `powerbi/` : fichier du tableau de bord Power BI associé au projet.

## Démarche

1. Importation et exploration des données.
2. Suppression des colonnes entièrement vides et traitement des doublons.
3. Remplacement des codes `-200` par des valeurs manquantes, puis imputation.
4. Détection des valeurs aberrantes avec la méthode IQR.
5. Analyse des distributions, corrélations et variations saisonnières.
6. Entraînement d'une régression linéaire pour prédire `NO2(GT)`.
7. Comparaison des valeurs observées et estimées.

## Résultats enregistrés

Les sorties du notebook indiquent :
- 113 doublons détectés avant déduplication ;
- 2 183 observations comportant au moins une valeur identifiée comme aberrante (23,33 % du jeu traité) ;
- coefficient de détermination R² : 0,75 ;
- erreur quadratique moyenne MSE : 475,50.

Dans l'analyse saisonnière enregistrée, les moyennes les plus élevées pour NOx et NO₂ apparaissent en hiver (respectivement 344,24 et 137,28, dans les unités du jeu de données).

Ces valeurs sont les résultats consignés dans les notebooks fournis. Elles ne constituent pas une validation indépendante du modèle.

## Environnement technique

Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Scikit-learn, Jupyter Notebook et Power BI.

## Installation

```bash
pip install -r requirements.txt
```

Ouvrir ensuite les notebooks avec Jupyter Notebook ou JupyterLab.

## Source des données

UCI Machine Learning Repository — Air Quality Data Set:
https://archive.ics.uci.edu/dataset/360/air+quality

Consulter la page de la source pour les informations de citation et les conditions de réutilisation des données.

## Points de vigilance méthodologiques

- Le notebook effectue l'imputation avant la séparation entraînement/test : les résultats peuvent donc être affectés par une fuite de données.
- Le découpage aléatoire ne tient pas compte de l'ordre temporel des observations. Une validation chronologique serait pertinente pour une utilisation prédictive dans le temps.
- Le MSE est exprimé dans l'unité au carré de la variable cible ; une RMSE et une MAE permettraient de compléter l'évaluation.
- Les résultats doivent être interprétés dans le contexte du jeu de données et de ses limites.

## Auteur

**Marcel BABELANA**  
Data Analyst | Business Intelligence | Python | SQL | Power BI

LinkedIn : ajouter le lien de votre profil.
