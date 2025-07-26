# Prédiction des Crises Systémiques en Afrique

## 🎯 Objectif

L'objectif de ce projet est de prédire l’émergence d'une **crise systémique** à partir d'indicateurs économiques (comme les taux d'inflation annuels), en utilisant un modèle de **Machine Learning**.  
Nous utiliserons pour cela un ensemble de données issues de **Kaggle**, couvrant les périodes de **1860 à 2014**, dans **13 pays africains**.

## 🌍 Description du Jeu de Données

Le jeu de données traite des crises :

- Bancaires (`banking_crisis`)
- De la dette
- Financières
- De l'inflation
- Systémiques (`systemic_crisis`)

### 📌 Pays concernés :
Afrique du Sud, Algérie, Angola, Côte d'Ivoire, Égypte, Kenya, Maroc, Maurice, Nigeria, République centrafricaine, Tunisie, Zambie, Zimbabwe.

📎 **Lien vers l’aperçu du jeu de données** :  
![Aperçu](https://i.imgur.com/3XzFz3x.jpg)

---

## 📊 Étapes du Projet

### 1. Importation et Exploration des Données

- Chargement du dataset avec `pandas`
- Aperçu général (`.head()`, `.info()`, `.describe()`)
- Création d'un rapport de profilage avec `pandas_profiling` ou `ydata-profiling`

### 2. Nettoyage des Données

- Suppression des doublons
- Traitement des valeurs manquantes
- Détection et gestion des valeurs aberrantes (z-score, boxplot…)

### 3. Prétraitement

- Encodage de la variable `banking_crisis` (`crisis` = 1, `no_crisis` = 0)
- Encodage de la variable `country` avec `pd.get_dummies()` (encodage OneHot)
- Normalisation/Standardisation des caractéristiques

### 4. Sélection des Variables

- Variable cible : `systemic_crisis`
- Variables explicatives : autres colonnes pertinentes
- Vérification des corrélations (`df.corr()`)

### 5. Séparation des Données

- Division en `X_train`, `X_test`, `y_train`, `y_test` (avec `train_test_split`)

### 6. Entraînement du Modèle

- Modèle choisi : `RandomForestClassifier`
- Ajustement de l’hyperparamètre `n_estimators`
- Entraînement sur l’ensemble d’apprentissage

### 7. Évaluation du Modèle

- Précision (`accuracy_score`)
- Rapport de classification (`classification_report`)
- Matrice de confusion (`confusion_matrix`)

#### ✅ Résultat Exemple :

```text
Accuracy: 0.995
Classification Report:
               precision    recall  f1-score   support

           0       0.99      1.00      1.00       194
           1       1.00      0.94      0.97        18

    accuracy                           1.00       212
   macro avg       1.00      0.97      0.98       212
weighted avg       1.00      1.00      1.00       212
💡 Améliorations Possibles
Utiliser la recherche d’hyperparamètres avec GridSearchCV

Comparer plusieurs algorithmes (Logistic Regression, SVM, XGBoost…)

Réduire la dimension avec PCA

Tester l'équilibre des classes avec SMOTE si déséquilibre

Visualisations avancées des arbres du Random Forest (ex: dtreeviz)

🧑‍💻 Auteur: Cheikh Niang
Projet réalisé dans le cadre d’un checkpoint de formation

Dataset fourni par Kaggle
