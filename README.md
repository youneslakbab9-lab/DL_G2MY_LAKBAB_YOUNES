# FootAI — Projet Deep Learning

## Présentation générale

FootAI est un projet de fin de module en **Deep Learning** appliqué au domaine du football.

L’objectif du projet est d’étudier et de comparer plusieurs architectures de réseaux de neurones selon la nature des données utilisées :

1. **MLP** pour les données tabulaires issues de StatsBomb.
2. **CNN** pour la classification d’images à partir de crops extraits d’annotations Roboflow/YOLO.
3. **RNN, LSTM, GRU et Seq2Seq** pour la classification et la génération de séquences textuelles footballistiques.

Le projet montre que le choix d’une architecture dépend fortement du type de données traité.
Un MLP est adapté aux données tabulaires, un CNN est plus performant pour les images, tandis que les modèles récurrents sont adaptés aux séquences.

---

## Informations du projet

**Module :** Deep Learning
**Projet :** FootAI
**Thème :** Modèles de Deep Learning pour données tabulaires, images et séquences
**Établissement :** École Marocaine des Sciences de l’Ingénieur
**Année universitaire :** 2025–2026

**Réalisé par :** Younes LAKBAB
**Encadré par :** Pr. BATAL Mossab

---

## Structure du repository

Le repository est organisé comme suit :

```text
DL_G2MY_LAKBAB_YOUNES/
│
├── README.md
│
├── Deep_Learning_Projet.pdf
│
└── notebooks/
    ├── 01_Partie_1_MLP_StatsBomb.ipynb
    ├── 02_Partie_2_CNN_Roboflow_YOLO.ipynb
    └── 03_Partie_3_RNN_LSTM_GRU_Seq2Seq.ipynb
```

---

## Contenu des fichiers

### `README.md`

Ce fichier présente l’idée générale du projet, la structure du repository et le rôle de chaque partie.

### `Deep_Learning_Projet.pdf`

Ce fichier contient le rapport complet du projet.
Il présente la partie théorique, la démarche expérimentale, les résultats obtenus, les analyses critiques et la conclusion générale.

### `notebooks/`

Ce dossier contient les trois notebooks Jupyter du projet :

* `01_Partie_1_MLP_StatsBomb.ipynb`
* `02_Partie_2_CNN_Roboflow_YOLO.ipynb`
* `03_Partie_3_RNN_LSTM_GRU_Seq2Seq.ipynb`

---

## Partie I — MLP sur données tabulaires StatsBomb

La première partie traite des données tabulaires issues des tirs de football StatsBomb.

Objectifs principaux :

* charger et préparer les données StatsBomb ;
* nettoyer, encoder et normaliser les variables ;
* construire un modèle MLP avec PyTorch ;
* comparer `nn.Sequential` et une classe personnalisée `nn.Module` ;
* tester plusieurs initialisations : gaussienne, constante et Xavier ;
* sauvegarder et recharger le modèle avec `state_dict` ;
* évaluer le modèle avec accuracy, précision, rappel, F1-score et matrice de confusion.

Cette partie montre que le MLP est adapté aux données tabulaires, mais que ses performances dépendent fortement de la qualité des variables et de la taille du dataset.

---

## Partie II — CNN sur images Roboflow/YOLO

La deuxième partie traite des images extraites à partir d’un dataset Roboflow au format YOLOv8.

Objectifs principaux :

* télécharger un dataset Roboflow/YOLO ;
* générer des crops à partir des bounding boxes ;
* entraîner un MLP sur images aplaties ;
* entraîner plusieurs CNN ;
* étudier l’effet du padding, du stride, du pooling, du nombre de filtres et de la convolution `1×1` ;
* visualiser les feature maps ;
* évaluer les modèles à l’aide des métriques de classification et d’une matrice de confusion.

Les résultats montrent que les CNN sont plus performants que les MLP pour les images, car ils exploitent la structure spatiale des données.

---

## Partie III — RNN, LSTM, GRU et Seq2Seq

La troisième partie traite des séquences textuelles footballistiques construites à partir d’événements StatsBomb.

Objectifs principaux :

* construire un corpus textuel footballistique ;
* créer un vocabulaire ;
* gérer la tokenisation et le padding ;
* entraîner des modèles RNN, LSTM et GRU pour la classification de séquences ;
* utiliser le gradient clipping ;
* construire un modèle Seq2Seq encodeur-décodeur ;
* utiliser le teacher forcing ;
* comparer le greedy decoding et le beam search ;
* évaluer la génération avec le score BLEU.

Cette partie montre que les modèles récurrents sont adaptés au traitement des séquences, mais que les résultats doivent être interprétés avec prudence car le corpus est construit à partir de templates.

---

## Technologies utilisées

Le projet utilise principalement :

* Python
* Jupyter Notebook
* Google Colab
* PyTorch
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* StatsBomb Open Data
* Roboflow
* YOLOv8

---

## Installation des bibliothèques principales

Pour exécuter les notebooks, il est recommandé d’utiliser Google Colab.

Les principales bibliothèques nécessaires sont :

```bash
pip install torch torchvision torchaudio
pip install numpy pandas matplotlib scikit-learn
pip install roboflow
```

---

## Ordre d’exécution recommandé

Les notebooks doivent être exécutés dans l’ordre suivant :

1. `01_Partie_1_MLP_StatsBomb.ipynb`
2. `02_Partie_2_CNN_Roboflow_YOLO.ipynb`
3. `03_Partie_3_RNN_LSTM_GRU_Seq2Seq.ipynb`

L’exécution sur Google Colab est recommandée, surtout pour les parties CNN et RNN qui peuvent bénéficier du GPU.


## Résultats principaux

Les résultats obtenus montrent que :

* le MLP est pertinent pour une classification tabulaire simple ;
* le CNN surpasse le MLP aplati pour la classification d’images ;
* les modèles RNN, LSTM et GRU sont efficaces pour les séquences textuelles structurées ;
* le modèle Seq2Seq permet de générer des phrases footballistiques simples ;
* le choix de l’architecture doit toujours être adapté à la nature des données.

---

## Conclusion

Ce projet met en évidence l’importance du choix de l’architecture en Deep Learning.

Les données tabulaires, les images et les séquences n’ont pas la même structure.
Il est donc nécessaire d’utiliser un modèle adapté à chaque type de données :

* **MLP** pour les vecteurs tabulaires ;
* **CNN** pour les images ;
* **RNN/LSTM/GRU/Seq2Seq** pour les séquences.

FootAI illustre ainsi le rôle central du biais inductif dans la réussite d’un projet de Deep Learning.
