# 🅿️ Parking Detection — Computer Vision & Deep Learning

Classification automatique des places de stationnement (libre, occupée, indéterminée) par CNN et Transfer Learning.

---

## 📌 Objectif

Détecter l'état des places de stationnement à partir d'images en comparant plusieurs architectures de réseaux de neurones convolutifs, allant du CNN from scratch jusqu'au Transfer Learning avec ResNet18 et VGG16.

---

## 📊 Dataset

- **Classes** : 3 — Place libre (0), Place occupée (1), Indéterminée (2)
- **Split** : 70% entraînement / 15% validation / 15% test
- **Prétraitement** : Normalisation dataset (baseline) et normalisation ImageNet (Transfer Learning)

---

## 🛠️ Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

---

## 🔍 Structure du projet

### Partie 1 — Préparation des données
- Chargement et split fixe 70/15/15
- Calcul mean/std sur le train
- Transforms baseline et ImageNet

### Partie 2 — CNN Baseline (from scratch)

| Modèle | Accuracy Test | F1-score | Temps |
|--------|--------------|----------|-------|
| CNN V1 (simple) | ~65% | ~64% | ~15 min |
| CNN V2 (BatchNorm + Dropout) | 68.75% | 68.20% | 20 min |

### Partie 3 — CNN avec Augmentation de données

| Augmentation | Accuracy Test | F1-score | Temps |
|-------------|--------------|----------|-------|
| Aug1 — Flip + Rotation | **71.02%** | **70.55%** | 31 min |
| Aug2 — Flip + Couleurs | 68.18% | ~67% | 36 min |

> L'augmentation par flip et rotation améliore la robustesse du modèle aux variations d'angle de caméra.

### Partie 4 — Transfer Learning

| Modèle | Accuracy Test | F1-score | Temps |
|--------|--------------|----------|-------|
| ResNet18 — Feature Extraction | 78.98% | ~78% | 30 min |
| **ResNet18 — Fine Tuning ✅** | **89.77%** | **89.10%** | **9 min** |
| VGG16 — Feature Extraction | 85.80% | ~85% | 20 min |

### Partie 5 — Analyse et Conclusion

| Modèle | Accuracy | F1-score | Temps |
|--------|----------|----------|-------|
| CNN V2 (baseline) | 68.75% | 68.20% | 20 min |
| CNN V2 + Aug1 | 71.02% | 70.55% | 31 min |
| **ResNet18 Fine Tuning** ✅ | **89.77%** | **89.10%** | **9 min** |

---

## 🏆 Meilleur modèle — ResNet18 Fine Tuning

- Accuracy de **89.77%** et F1-score de **89.10%**
- Entraînement le plus rapide grâce à l'early stopping (9 min)
- Généralise très bien sur les 3 classes avec peu d'erreurs
- Meilleur choix pour une utilisation réelle

---

## 📁 Structure du repo

```
parking-detection-ai/
│
├── parking_detection.ipynb   # Notebook complet — CNN, augmentation, Transfer Learning
└── README.md
```

---

## 👤 Auteur

**Mohamed Ramy Boulkaraa**  
Étudiant en Intelligence Artificielle — La Cité, Ottawa  
[GitHub](https://github.com/boulkaraamohamedramy)
