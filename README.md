# 🏠 Prédiction du Prix Immobilier — California Housing

Projet de machine learning de bout en bout sur le dataset **California Housing**.

---

## 📌 Problème traité

Prédire la **valeur médiane des logements** (en 100 000 $) pour des blocs de
recensement en Californie (données 1990). C'est un problème de **régression supervisée**.

---

## 📁 Dataset

| Propriété | Valeur |
|---|---|
| Source | UCI / scikit-learn (`fetch_california_housing`) |
| Lignes | 20 640 |
| Features | 8 (numériques) |
| Cible | `MedHouseVal` — valeur médiane (100k$) |

**Variables** : MedInc, HouseAge, AveRooms, AveBedrms, Population,
AveOccup, Latitude, Longitude.

---

## 🛠️ Pipeline

```
Dataset → Nettoyage → Split 80/20 → Normalisation → Modèles → Évaluation → Interface
```

**Prétraitement** :
- Suppression des outliers (quantile 99%) sur AveRooms et AveOccup
- Normalisation StandardScaler (pour la régression linéaire)

**Partie non supervisée (bonus)** :
- PCA 2D pour visualiser la structure des données
- K-Means (k=4) pour segmenter les logements

---

## 📊 Résultats

| Modèle | MAE | RMSE | R² |
|---|---|---|---|
| Régression Linéaire | ~0.53 | ~0.72 | ~0.59 |
| Random Forest | ~0.33 | ~0.50 | **~0.80** |
| Gradient Boosting | ~0.37 | ~0.53 | ~0.77 |

🏆 **Meilleur modèle : Random Forest** (R² ≈ 0.80)

---

## ▶️ Lancer le projet

### 1. Installer les dépendances

```bash
pip install -r requirements.txt
```

### 2. Ouvrir le notebook

```bash
jupyter notebook notebook.ipynb
```

### 3. Exécuter toutes les cellules

`Kernel` → `Restart & Run All`

La dernière cellule affiche une **interface interactive** (widgets) pour
prédire le prix d'un logement en ajustant des sliders.

---

## 📦 Structure du projet

```
housing_prediction/
├── notebook.ipynb          ← Pipeline complet + interface
├── requirements.txt        ← Dépendances Python
├── README.md               ← Ce fichier
└── rapport.pdf             ← Rapport PDF (7-10 pages)
```

---

## 👥 Auteurs

- Étudiant 1 — [Prénom Nom]
- Étudiant 2 — [Prénom Nom]
