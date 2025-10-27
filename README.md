# Analyse comparative de la performance scolaire – Dataset Kaggle *Student Alcohol Consumption*
## English version below

Ce projet a pour objectif d’analyser les facteurs influençant la performance scolaire des élèves à partir des datasets [**student-mat.csv** et **student-por.csv**](https://www.kaggle.com/datasets/uciml/student-alcohol-consumption/data) issus de Kaggle.
L’étude s’appuie sur une approche **supervisée et non supervisée**, combinant des techniques de **sélection de variables** et des **modèles d’ensemble learning** pour la prédiction des résultats scolaires.

---

## Objectifs du projet

* Identifier les variables les plus influentes sur la note finale (**G3**).
* Comparer différentes méthodes de sélection de variables (**SVM**, **PCA**, **RFE**, **Random Forest**).
* Évaluer la performance de plusieurs modèles d’ensemble (**Decision Tree**, **Random Forest**, **AdaBoost**, **Bagging**).
* Étudier la robustesse des modèles selon le nombre de variables sélectionnées (**K**).
* Comparer les résultats entre les deux matières : **Mathématiques** et **Portugais**.

---

## Étapes du notebook

### 1. Chargement et préparation des données

Importation des deux jeux de données, sélection des variables numériques et séparation entre variables explicatives (**X**) et cible (**y = G3**).
Les données sont normalisées afin d’assurer la comparabilité entre les features.

### 2. Sélection de variables

* **Méthodes basées sur les modèles** : SVM, Logistic Regression et Random Forest.
* **PCA** : approche non supervisée pour identifier les composantes de plus grande variance.
* **RFE** : sélection itérative avec régression logistique.
  Les résultats mettent en évidence la stabilité des variables **G1** et **G2**, très corrélées à la note finale.

### 3. Comparaison des méthodes d’ensemble learning

Entraînement des modèles **Decision Tree**, **Random Forest**, **AdaBoost** et **Bagging** sur les variables sélectionnées.
Évaluation par **validation croisée** (KFold, 5 folds) et mesure de la **précision moyenne (Accuracy)** pour différents **K** (2, 5, 8).

### 4. Passage au multiclass

Transformation de la variable cible en quatre classes de performance : *faible*, *moyen*, *bon*, *excellent*.
Les modèles sont réentraînés et comparés sur cette nouvelle échelle.

### 5. Analyse des résultats et interprétation

* Pour le dataset **MATH**, les modèles simples (Decision Tree) suffisent à atteindre de très bonnes performances, portées par la forte corrélation entre **G1**, **G2** et **G3**.
* Pour le dataset **POR**, les modèles d’ensemble (Bagging, Random Forest) généralisent mieux, traduisant une plus grande hétérogénéité des profils d’élèves.
* Les performances élevées liées à **G1** et **G2** rappellent que ces variables prédisent une continuité de résultats plus qu’une véritable causalité.

---

## Structure du code

* **Partie 1 :** Préparation et normalisation des données
* **Partie 2 :** Sélection de variables (SVM, PCA, RFE)
* **Partie 3 :** Implémentation des modèles d’ensemble
* **Partie 4 :** Validation croisée et comparaison des performances
* **Partie 5 :** Analyse comparative et conclusions

---

## Conclusion

L’étude met en évidence la cohérence des variables liées aux performances passées (**G1**, **G2**) et l’influence secondaire des facteurs sociaux et familiaux (**Fedu**, **Medu**, **Walc**, **absences**).
Les modèles d’ensemble offrent une meilleure robustesse sur les profils d’élèves variés, tandis que les modèles simples suffisent lorsque la corrélation entre les notes est forte.
Ce travail illustre l’importance de combiner **sélection de variables**, **apprentissage supervisé** et **validation croisée** pour interpréter correctement la performance prédictive d’un modèle.

---


# Comparative Analysis of Academic Performance – Kaggle *Student Alcohol Consumption* Dataset

This project aims to analyze the factors influencing students’ academic performance using the [**student-mat.csv** and **student-por.csv**](https://www.kaggle.com/datasets/uciml/student-alcohol-consumption/data) datasets from Kaggle.
The study combines **supervised and unsupervised approaches**, integrating **feature selection techniques** and **ensemble learning models** to predict students’ final grades.

---

## Project Objectives

* Identify the most influential variables on the final grade (**G3**).
* Compare different feature selection methods (**SVM**, **PCA**, **RFE**, **Random Forest**).
* Evaluate the performance of various ensemble models (**Decision Tree**, **Random Forest**, **AdaBoost**, **Bagging**).
* Assess the robustness of models depending on the number of selected features (**K**).
* Compare results between the two subjects: **Mathematics** and **Portuguese**.

---

## Notebook Steps

### 1. Data Loading and Preparation

We import both datasets, select numerical variables, and separate explanatory variables (**X**) from the target (**y = G3**).
Data is normalized to ensure comparability between features.

### 2. Feature Selection

* **Model-based methods:** SVM, Logistic Regression, and Random Forest.
* **PCA:** unsupervised approach identifying major variance components.
* **RFE:** iterative feature elimination using Logistic Regression.
  Results highlight the consistency of **G1** and **G2**, which are highly correlated with the final grade.

### 3. Comparison of Ensemble Learning Methods

We train **Decision Tree**, **Random Forest**, **AdaBoost**, and **Bagging** models on the selected variables.
Evaluation is performed using **5-fold cross-validation**, measuring **average accuracy** for different **K** values (2, 5, 8).

### 4. Transition to Multiclass Classification

We transform the target variable into four performance classes: *low*, *average*, *good*, *excellent*.
The models are retrained and compared under this new configuration.

### 5. Results Analysis and Interpretation

* For the **MATH** dataset, simple models (Decision Tree) achieve strong results due to the high correlation between **G1**, **G2**, and **G3**.
* For the **POR** dataset, ensemble models (Bagging, Random Forest) generalize better, reflecting greater variability among students.
* The high accuracy related to **G1** and **G2** confirms that these features represent grade continuity rather than true causal factors.

---

## Code Structure

* **Part 1:** Data preparation and normalization
* **Part 2:** Feature selection (SVM, PCA, RFE)
* **Part 3:** Ensemble models implementation
* **Part 4:** Cross-validation and performance comparison
* **Part 5:** Comparative analysis and conclusions

---

## Conclusion

The study highlights the consistency of past performance indicators (**G1**, **G2**) and the secondary influence of social and family factors (**Fedu**, **Medu**, **Walc**, **absences**).
Ensemble models offer greater robustness across diverse student profiles, while simple models suffice when grade correlations are strong.
This work demonstrates the importance of combining **feature selection**, **supervised learning**, and **cross-validation** to interpret a model’s predictive performance accurately.


