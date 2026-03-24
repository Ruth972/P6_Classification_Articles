# 🛒 Moteur de Classification d'Articles E-commerce (NLP & Computer Vision)

![Python](https://img.shields.io/badge/Python-3.10+-3776ab?style=flat)
![NLP](https://img.shields.io/badge/NLP-NLTK_%7C_BERT_%7C_USE-ff69b4?style=flat)
![Vision](https://img.shields.io/badge/Vision-OpenCV_%7C_Keras-ff9900?style=flat)
![Task](https://img.shields.io/badge/Task-Clustering_%7C_Classification-4caf50?style=flat)

Ce dépôt contient mon travail pour le Projet 6 du parcours Data Scientist d'OpenClassrooms. Il est divisé en deux missions principales visant à automatiser l'attribution de catégories pour les articles d'une marketplace e-commerce ("Place de marché").

## 📝 Contexte du Projet

Actuellement, l'attribution des catégories d'articles est faite manuellement par les vendeurs, ce qui est source d'erreurs et freine le passage à l'échelle. L'objectif est de développer un moteur de classification automatique en exploitant à la fois les données textuelles (descriptions en anglais) et visuelles (photos des produits).

---

## 📂 Partie 1 : Étude de faisabilité d'un moteur de classification
**Notebook associé :** `Etudiez la faisabilité d'un moteur de classification d'articles.ipynb`

L'objectif de cette première phase est de prouver qu'il est possible de regrouper automatiquement les produits de même catégorie (approche non supervisée).

**Méthodologie NLP (Traitement du texte) :**
* **Prétraitement :** Nettoyage, tokenization, stop-words, lemmatization.
* **Approches classiques :** Bag-of-Words (BoW), TF-IDF.
* **Word/Sentence Embeddings :** Word2Vec, BERT, Universal Sentence Encoder (USE).

**Méthodologie Computer Vision (Traitement de l'image) :**
* **Prétraitement :** Passage en niveaux de gris, filtrage du bruit, ajustement du contraste.
* **Extraction classique :** Algorithmes SIFT / ORB.
* **Deep Learning :** Transfer Learning avec des réseaux CNN pré-entraînés (ex: VGG16, ResNet).

**Résultats de l'étude (Partie 1) :**
* Les projections en 2 dimensions (PCA, t-SNE) et la mesure de similarité (score ARI) ont démontré que les modèles basés sur les Transformers (USE, BERT) pour le texte, et le Transfer Learning (CNN) pour l'image, offrent les meilleures performances pour regrouper les articles par catégorie réelle.

---

## 📂 Partie 2 : Classification supervisée d'images & API
**Notebook associé :** `Réalisez une classification supervisée d'images.ipynb`

Suite à la validation de la faisabilité, cette seconde phase se concentre sur la création d'un modèle prédictif et l'enrichissement de la base de données.

**Méthodologie et Objectifs :**
* **Classification Supervisée :** Entraînement d'un modèle de classification d'images pour prédire directement la catégorie du produit.
* **Data Augmentation :** Application de transformations (rotations, zooms, flips) sur les images d'entraînement pour enrichir le dataset, limiter le surapprentissage et optimiser les performances du modèle.
* **Collecte de données (API) :** Développement d'un script Python requêtant l'API **OpenFoodFacts** pour collecter de nouveaux produits d'épicerie fine (ex: produits à base de champagne) et les exporter au format `.csv` (foodId, label, category, foodContentsLabel, image).

---

## 🚀 Instructions d'Exécution

Pour exécuter les notebooks en local :
1. Clonez ce dépôt.
2. Installez les dépendances nécessaires (Keras, TensorFlow, NLTK, Scikit-Learn, OpenCV).
3. Assurez-vous d'avoir téléchargé le jeu de données des articles fourni par OpenClassrooms et de mettre à jour les chemins d'accès (`paths`) dans les premières cellules des notebooks.
