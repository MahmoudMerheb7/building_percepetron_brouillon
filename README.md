# **README: Analyse des Données et Modélisation avec le Perceptron**

## **Introduction**
Ce projet est une analyse des données relatives à un problème de classification binaire des tumeurs (étiquettes bénignes ou malignes) à partir de caractéristiques calculées sur des images de masses. Les étapes incluent la préparation des données, la réduction de dimensionnalité via l’ACP (Analyse en Composantes Principales), et l’entraînement d’un perceptron personnalisé.

---

## **Fonctionnalités principales**
- Chargement et préparation des données avec standardisation.
- Analyse exploratoire des données : visualisations (distributions, corrélations, boxplots).
- Réduction de dimensionnalité via l’Analyse en Composantes Principales (ACP).
- Implémentation et entraînement d’un perceptron personnalisé pour la classification binaire.
- Évaluation des performances du modèle avec des métriques clés (précision, courbes ROC et Précision-Rappel).

---

## **Installation**
### **Prérequis :**
- Python 3.x
- Bibliothèques : `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

### **Instructions :**
1. Clonez le dépôt :
   ```bash
   git clone https://github.com/username/project.git
   ```
2. Accédez au dossier du projet :
   ```bash
   cd project
   ```
3. Installez les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

---

## **Utilisation**
### **1. Exécuter le notebook :**
Le fichier `notebook.ipynb` contient toutes les étapes d'analyse et de modélisation. Lancez-le avec :
   ```bash
   jupyter notebook notebook.ipynb
   ```

### **2. Script Python :**
Si vous souhaitez exécuter uniquement le perceptron personnalisé, utilisez le fichier `perceptron.py`. Exemple d'utilisation :
   ```bash
   python perceptron.py
   ```

---

## **Structure des fichiers**
- `data.csv` : Données brutes du projet.
- `notebook.ipynb` : Notebook contenant l'analyse complète et les visualisations.
- `perceptron.py` : Fichier Python implémentant le perceptron personnalisé.
- `requirements.txt` : Liste des dépendances pour le projet.

---

## **Résultats principaux**
- **Modèle utilisé :** Perceptron personnalisé.
- **Performance :**
  - Précision globale : 97.37 %
  - ROC-AUC : 1.00

Ces résultats montrent que le perceptron fonctionne très bien sur ce problème, grâce à une forte linéarité des données après réduction dimensionnelle via ACP.

---

## **Limitations et améliorations possibles**
1. **Validation croisée :** Tester le modèle sur différents sous-ensembles pour confirmer la robustesse.
2. **Gestion du déséquilibre des classes :** Utiliser des techniques comme le sur/sous-échantillonnage ou pondérer les classes.
3. **Modèles avancés :** Explorer des modèles comme SVM ou réseaux de neurones pour des données plus complexes.
4. **Extension des données :** Ajouter des jeux de données variés pour généraliser les performances du modèle.

---

## **Contributeurs**
- Auteur : [Votre Nom ou Pseudonyme]
- Contributions ouvertes via pull requests.

---

## **Licence**
Ce projet est sous licence MIT. Consultez le fichier `LICENSE` pour plus d'informations.


