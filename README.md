# Traitement des valeurs manquantes : base Water Potability

Projet de Data Mining (IIT, Sfax).

## Objectif
Comparer plusieurs méthodes de traitement des valeurs manquantes sur la colonne `Sulfate` (≈ 24 % de valeurs manquantes) de la base Water Potability (Kaggle, cible : `Potability`).

## Méthodes comparées
Suppression, moyenne, médiane, mode, constante, bfill, ffill, interpolation linéaire, KNN.

## Évaluation
Comparaison des distributions (moyenne, médiane, écart-type, skewness, boxplots) avant et après imputation.
[Si tu as ajouté la cellule RMSE : « Puis mesure de l'erreur (RMSE) en cachant 20 % des valeurs connues. »]

## Résultats
[Écris ici ta conclusion : la méthode la plus adaptée et pourquoi, en 2 phrases.]

## Utilisation
Notebook écrit pour Google Colab (Python 3, pandas, seaborn, scikit-learn). Télécharger `water_potability.csv` depuis Kaggle et adapter le chemin du fichier dans le notebook.
