# Traitement des valeurs manquantes : base Water Potability

Projet de Data Mining (IIT, Sfax).

## Objectif
Comparer plusieurs méthodes de traitement des valeurs manquantes sur la colonne `Sulfate` de la base Water Potability (Kaggle, cible : `Potability`). La colonne compte 781 valeurs manquantes sur 3 276 (≈ 24 %).

## Méthodes comparées
Suppression, moyenne, médiane, mode, constante, bfill, ffill, interpolation linéaire, KNN.

## Évaluation
Pour chaque méthode, comparaison de la distribution de `Sulfate` avant et après imputation (moyenne, médiane, écart-type, skewness, histogrammes, boxplots).

## Résultats
| Méthode | Moyenne | Écart-type | Skewness |
|---|---|---|---|
| Original (sans valeurs manquantes) | 333,78 | 41,42 | -0,04 |
| Moyenne | 333,78 | 36,14 | -0,04 |
| Médiane | 333,61 | 36,14 | -0,03 |
| Mode | 284,96 | 94,46 | -0,74 |
| Constante (100) | 278,04 | 105,98 | -0,84 |
| ffill | 333,95 | 41,26 | -0,01 |
| Interpolation | 333,74 | 38,87 | -0,03 |
| KNN | 333,61 | 37,45 | -0,03 |

**Conclusion :**
- La distribution de `Sulfate` est quasi symétrique (skewness ≈ -0,04) : la moyenne et la médiane sont proches et conviennent comme valeurs de remplacement.
- Le mode et la constante déforment fortement la distribution (moyenne qui chute à 278-285, skewness autour de -0,8, écart-type plus que doublé) : ils sont à éviter.
- La moyenne et la médiane conservent la moyenne mais réduisent l'écart-type (36,14 contre 41,42). L'interpolation et le KNN réduisent moins la dispersion (38,87 et 37,45).
- ffill et bfill préservent le mieux l'écart-type, mais ils supposent un ordre significatif des lignes, ce qui n'est pas le cas de cette base. bfill laisse en plus 4 valeurs manquantes en fin de colonne.
- Le KNN, qui exploite les autres variables, est un bon compromis.

## Utilisation
Notebook écrit pour Google Colab (Python 3, pandas, seaborn, scikit-learn). Télécharger `water_potability.csv` depuis Kaggle et adapter le chemin du fichier dans le notebook.
