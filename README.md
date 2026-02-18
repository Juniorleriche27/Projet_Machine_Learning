# Projet Phase 2 - D-CLIC OIF

Ce projet predit:
- la consommation d'energie (`SiteEnergyUse(kBtu)`)
- les emissions de CO2 (`TotalGHGEmissions`)

Le travail est organise en 3 notebooks livrables:
- `general.ipynb`
- `02_modele_energie.ipynb`
- `03_modele_co2.ipynb`

Des copies corrigees sont disponibles pour renforcer la reproductibilite et la rigueur d'evaluation:
- `general_v2.ipynb`
- `02_modele_energie_v2.ipynb`
- `03_modele_co2_v2.ipynb`

## Donnees et artefacts

- Donnee source: `2016_Building_Energy_Benchmarking.csv`
- Donnee nettoyee: `df_fe_clean.csv`
- Pack modele: `model_data_phase2.joblib`, `model_data_phase2_v2.joblib`

## Reproductibilite

1. Creer l'environnement:
```powershell
python -m venv .venv
.\.venv\Scripts\activate
```

2. Installer les dependances:
```powershell
pip install -r requirements_phase2.txt
```

3. Executer les notebooks dans cet ordre:
```text
general.ipynb
02_modele_energie.ipynb
03_modele_co2.ipynb
```

4. Version corrigee recommandee pour la soutenance:
```text
general_v2.ipynb
02_modele_energie_v2.ipynb
03_modele_co2_v2.ipynb
```

## Corrections integrees dans les notebooks v2

- Chemin relatif pour le chargement des donnees (pas de chemin absolu machine).
- Section de validation finale rigoureuse pour energie et CO2:
  - split `train/test`
  - split `train/val` pour early stopping
  - selection sur validation
  - evaluation finale unique sur test
