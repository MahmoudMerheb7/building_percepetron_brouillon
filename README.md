# **README: Analyse des Données et Modélisation avec le Perceptron**

## **Introduction**
Ce projet porte sur l’analyse des données relatives à un problème de classification binaire des tumeurs (étiquettes bénigne ou maligne) à partir de caractéristiques calculées sur des images de masses. Les étapes incluent la préparation des données, la visualisation, la réduction de dimensionnalité via l’ACP (Analyse en Composantes Principales), et l’entraînement d’un perceptron personnalisé.

---

## **Structure du Projet**

### **1. Chargement et préparation des données**
Les étapes principales incluent :
- Suppression des colonnes inutiles (étiquettes uniques, colonnes vides).
- Encodage de la variable cible (`diagnosis`) :
  - `M` (maligne) → 1.
  - `B` (bénigne) → 0.
- Standardisation des caractéristiques à l’aide de `StandardScaler`.

### **2. Visualisation des données**
#### **Distribution de la variable cible**
Un graphique à barres permet de visualiser le déséquilibre entre les classes bénignes et malignes.

#### **Histogrammes des caractéristiques**
- Les caractéristiques sont séparées en trois groupes :
  - Moyennes (`_mean`).
  - Erreurs standards (`_se`).
  - Valeurs maximales (`_worst`).
- Les distributions montrent des différences marquées entre les classes pour certaines variables (échelle, taille, et régularité des contours).

#### **Boxplots**
- Les boxplots révèlent une nette séparation des classes pour des caractéristiques comme `radius_mean` et `concave points_mean`.
- La classe maligne présente souvent des valeurs extrêmes, révélant une variabilité importante.

#### **Scatterplots des paires de variables**
- Les scatterplots montrent les relations entre les paires de variables principales (échantillons colorés selon `diagnosis`).
- Une forte corrélation est observée entre des variables comme `radius_mean` et `perimeter_mean`.

#### **Matrice de corrélation**
- Une heatmap met en évidence les fortes corrélations entre des groupes de variables redondantes, justifiant l’utilisation de l’ACP pour réduire la dimensionnalité.

### **3. Analyse en Composantes Principales (ACP)**
#### **Objectif :**
- Capturer la variance des données tout en réduisant le nombre de dimensions.

#### **Résultats :**
- Les 4 premières composantes principales expliquent plus de 70 % de la variance.
- Une visualisation de la variance expliquée montre la contribution cumulative des composantes principales.

#### **Contributions des variables :**
- Les variables comme `concave points_mean`, `radius_mean`, et `perimeter_mean` contribuent fortement à PC1, capturant les aspects liés à la taille et la forme des tumeurs.

### **4. Modélisation avec le perceptron**
#### **Perceptron personnalisé :**
Un perceptron a été implémenté manuellement avec les caractéristiques suivantes :
- **Fonction de coût :** Log-loss.
- **Mécanisme d’optimisation :** Descente de gradient.
- **Paramètres :** Taux d’apprentissage (0.01), nombre d’itérations (1000).

#### **Entraîment et prédictions :**
- Entraînement sur 80 % des données.
- Prédictions et évaluation sur les 20 % restants.

---

## **Résultats et interprétations**

### **Matrice de confusion :**
- **Vrais positifs (41)** : Tumeurs malignes correctement prédites.
- **Faux positifs (1)** : Tumeur bénigne incorrectement classée comme maligne.
- **Faux négatifs (2)** : Tumeurs malignes manquées.
- **Vrais négatifs (70)** : Tumeurs bénignes correctement prédites.

### **Courbe ROC et score ROC-AUC :**
- **ROC-AUC : 1.00** (parfait).
- Une séparation parfaite entre les classes est observée, ce qui pourrait être attribué à une forte linéarité des données après ACP.

### **Courbe Précision-Rappel :**
- Montre un bon compromis entre la précision et le rappel.

---

## **Conclusions**
- Le perceptron est très performant sur ce problème avec des données linéairement séparables.
- Cependant, les résultats doivent être validés avec des données plus complexes et éventuellement d’autres modèles (SVM, réseaux de neurones).

---

## **Améliorations possibles**
1. **Validation croisée :**
   - Tester le modèle sur différents sous-ensembles pour confirmer la robustesse.

2. **Gestion du déséquilibre des classes :**
   - Utiliser des techniques comme le sur/sous-échantillonnage ou pondérer les classes.

3. **Exploration de modèles avancés :**
   - SVM avec noyaux non linéaires.
   - Réseaux de neurones multicouches (MLP).

4. **Enrichissement des données :**
   - Obtenir un jeu de données plus large et varié.

---

## **Structure des fichiers**
- `data.csv` : Fichier contenant les données brutes.
- `perceptron.py` : Implémentation du perceptron personnalisé.
- `notebook.ipynb` : Analyse complète et modélisation dans un notebook interactif.

---

## **Dépendances**
- Python 3.x
- Bibliothèques : `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

---

## **Exécution**
1. Clonez le dépôt.
2. Installez les dépendances via pip :
   ```bash
   pip install -r requirements.txt
   ```
3. Lancez le notebook pour reproduire l’analyse :
   ```bash
   jupyter notebook notebook.ipynb
   ```
