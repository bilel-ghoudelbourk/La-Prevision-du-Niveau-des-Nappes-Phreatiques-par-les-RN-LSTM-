# Prévision du Niveau des Nappes Phréatiques par Réseaux de Neurones

![Python Version](https://img.shields.io/badge/Python-3.11.2-blue)

## Introduction
Ce projet vise à développer des modèles de réseaux de neurones pour prédire les niveaux des nappes phréatiques en Australie. Les données utilisées proviennent de plusieurs puits répartis dans différentes régions, chaque fichier contenant des observations mensuelles de variables environnementales (précipitations, température, évapotranspiration et indice de végétation) ainsi que les niveaux de la nappe phréatique (GWL).

## Structure du Projet

### 1. Visualisation et Étude de Corrélation

#### Valeurs Non Normalisées & Normalisées
Les graphiques montrent les données des variables environnementales avant et après normalisation. La normalisation des données transforme les valeurs pour avoir une moyenne de 0 et un écart type de 1, ce qui facilite la comparaison entre différentes variables sur une échelle commune.

#### Calcul du Coefficient de Concordance de Corrélation (CCC)
Les coefficients de corrélation entre le niveau de la nappe phréatique (GWL) et d'autres variables (ET, NDVI, P, T) sont calculés avant et après normalisation, quantifiant la relation linéaire entre ces variables.

### 2. Prédiction du Niveau des Nappes

#### Prétraitement de Données
Plusieurs méthodes ont été testées pour remplir les valeurs manquantes, y compris l’imputation par K-Nearest Neighbors (KNN), l’interpolation linéaire, et une combinaison des deux. La méthode KNN + interpolation linéaire a montré la meilleure performance et a été utilisée pour imputer les valeurs manquantes.

#### Modèle Spécifique à un Puits
Un modèle de réseau de neurones de type LSTM est utilisé pour chaque puits afin de modéliser les variations du niveau des nappes phréatiques. Le modèle est entraîné sur les données de chaque puits en utilisant toutes les observations sauf les 12 derniers mois, qui sont réservés pour le test.

#### Modèle Général Simple
Un modèle général est entraîné sur l’ensemble des données disponibles pour chaque puits, à l’exception des 12 derniers mois utilisés pour le test.

#### Modèle Général Fine-Tuned par Région
Le modèle général est affiné pour mieux s’adapter aux spécificités de chaque région (Victoria et Queensland).

#### Modèles Fine-Tuned par Puits
Les modèles sont ajustés spécifiquement pour chaque puits après un entraînement initial général.

## Conclusion
Ce projet met en évidence l’importance d’adapter les modèles de prédiction des niveaux des nappes phréatiques aux spécificités locales pour améliorer la précision et la fiabilité des prévisions. Des recherches futures pourraient explorer des modèles plus sophistiqués et intégrer des données supplémentaires pour affiner davantage les prédictions.

## Auteur

- **Nom:** GHOUDELBOURK
- **Prénom:** Bilel