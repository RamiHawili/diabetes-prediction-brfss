# Diabetes Prediction — BRFSS 2015

Projet de classification binaire pour prédire le risque de diabète à partir des données de l'enquête BRFSS 2015 (CDC).
Réalisé dans le cadre d'un projet Master IA — CESI FISE A4 (2025/2026).

---

## Contexte

Le diabète est l'une des maladies chroniques les plus répandues aux États-Unis. En 2018, les CDC estimaient à 34,2 millions le nombre d'Américains diabétiques, et à 88 millions ceux en état de prédiabète, dont une grande majorité ignorait leur situation. Son coût économique est estimé à près de 400 milliards de dollars par an.

Le dataset utilisé provient du Behavioral Risk Factor Surveillance System (BRFSS), une enquête téléphonique annuelle menée par les CDC auprès de plus de 400 000 Américains. La version 2015 contient 253 680 répondants et 22 variables relatives aux comportements de santé, antécédents médicaux et conditions socio-économiques.

---

## Objectif

Construire un modèle de classification binaire capable de prédire si une personne est diabétique à partir de ses indicateurs de santé, en maximisant la métrique ROC AUC sur un jeu de test non étiqueté.

Variable cible binarisée :
- 0 -> pas de diabète ou prédiabète (classes 0 et 1 regroupées)
- 1 -> diabète avéré (classe 2)

---

## Structure du projet

```
diabetes-prediction-brfss/
│
├── data/
│   ├── raw/                     # CSV source (non versionné)
│   └── processed/               # Datasets nettoyés et splits (non versionnés)
│
├── notebooks/
│   ├── Sprint1_Livrable.ipynb   # Prétraitement complet
│   ├── Sprint2_Livrable.ipynb   # Réseau de neurones (à venir)
│   └── Sprint3_Livrable.ipynb   # Optimisation avancée (à venir)
│
├── reports/
│   ├── figures/                 # Graphiques EDA
│   ├── sprint1/
│   ├── sprint2/
│   └── sprint3/
│
├── models/                      # Modèles sérialisés (non versionnés)
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Installation

```bash
git clone https://github.com/RamiHawili/diabetes-prediction-brfss.git
cd diabetes-prediction-brfss

python -m venv venv
venv\Scripts\activate        # Windows
# ou
source venv/bin/activate     # Linux / Mac

pip install -r requirements.txt
```

Dataset : télécharger le CSV depuis [Kaggle](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset) et le placer dans `data/raw/`.

---

## Sprints

### Sprint 1 — Prétraitement (notebooks/Sprint1_Livrable.ipynb)

| Etape | Description | Statut |
|-------|-------------|--------|
| 1 | Chargement et compréhension initiale | Terminé |
| 2 | Séparation cible / variables explicatives + binarisation | Terminé |
| 3 | Découpage train / val / test stratifié (70/15/15) | Terminé |
| 4 | Typage des variables | Terminé |
| 5 | Nettoyage des doublons et valeurs manquantes | Terminé |
| 6 | Analyse exploratoire quantitative | Terminé |
| 7 | EDA visuelle (6 figures) | Terminé |
| 8 | Normalisation StandardScaler (fit sur train uniquement) | Terminé |
| 9 | Sauvegarde des datasets nettoyés | Terminé |

Résultats clés :
- Dataset nettoyé : 229 474 lignes après suppression des doublons
- Déséquilibre des classes : environ 5.5 pour 1
- Top corrélations avec la cible : GenHlth, HighBP, BMI, DiffWalk, HighChol

---

### Sprint 2 — Modèle simple et évaluation initiale (à venir)

| Etape | Description |
|-------|-------------|
| 1 | Choix de l'architecture réseau |
| 2 | Construction du réseau de neurones |
| 3 | Entraînement et évaluation |
| 4 | Analyse du seuil de décision |
| 5 | Suivi des expérimentations |
| 6 | Rapport intermédiaire |

---

### Sprint 3 — Modèle avancé et interprétabilité (à venir)

| Etape | Description |
|-------|-------------|
| 1 | Architecture enrichie du modèle |
| 2 | Choix du framework de deep learning |
| 3 | Gestion du déséquilibre des classes |
| 4 | Intégration de l'IA explicable et développement durable |
| 5 | Rapport final |

---

## Résultats

| Sprint | Métrique | Score |
|--------|----------|-------|
| Sprint 1 | Prétraitement | Terminé |
| Sprint 2 | ROC AUC (val) | à compléter |
| Sprint 3 | ROC AUC (test) | à compléter |

---

## RGPD et Ethique

Le dataset BRFSS 2015 est anonymisé par les CDC : pas d'identifiants directs, âge regroupé en 13 tranches, origine ethnique absente. Le traitement est légitimé par l'art. 9.2.j RGPD (recherche en santé publique).

Points de vigilance :
- Variables socio-économiques (Income, Education) conservées pour leur pouvoir prédictif mais surveillées pour détecter les biais
- Le modèle n'est pas un dispositif médical et ne peut pas servir de décision automatisée individuelle (art. 22 RGPD)

---

## Auteur

Hawili Rami — [@RamiHawili](https://github.com/RamiHawili)
Master IA — CESI FISE A4 2025/2026
