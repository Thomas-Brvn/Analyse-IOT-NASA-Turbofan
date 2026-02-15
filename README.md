# Analyse de donnees IOT - NASA Turbofan Engine

## Contexte

Je n'avais jamais travaille avec des donnees IOT auparavant, et je voulais tester ca sur un dataset concret. J'ai choisi le dataset NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation) qui contient des donnees de capteurs de moteurs turbofan.

L'objectif est simple : explorer les donnees de capteurs et essayer de predire la duree de vie restante (RUL - Remaining Useful Life) des moteurs.

## Dataset

Le dataset FD001 contient :
- 100 moteurs en entrainement, 100 en test
- 21 capteurs par moteur
- 3 parametres operationnels

Source : NASA Prognostics Data Repository

## Installation

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

## Resultats

Trois modeles testes sur le dataset FD001 :

| Modele | RMSE (test) | MAE (test) | R2 (test) |
|--------|-------------|------------|-----------|
| Linear Regression | 20.85 | 16.64 | 0.73 |
| Random Forest | 17.03 | 11.94 | 0.82 |
| Gradient Boosting | 16.92 | 11.80 | 0.82 |

Le Gradient Boosting donne les meilleurs resultats avec un RMSE de ~17 cycles sur le test set.

## Contenu

- `nasa_turbofan_analysis.ipynb` : notebook principal avec l'analyse complete
- `data/CMaps/` : fichiers de donnees NASA (source : [NASA Prognostics Data Repository](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/))
