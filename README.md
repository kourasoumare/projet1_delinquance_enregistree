# Délinquance enregistrée en Loire-Atlantique (2016-2025)

Projet 1 – Exploration et restitution de données (UE01, DIA2).

## Contexte

**Commanditaire :** conseil intercommunal de sécurité et de prévention de la délinquance (fictif).

**Besoin exprimé :** « Nous renouvelons notre stratégie de prévention. Nous voulons savoir quels types de faits progressent sur notre territoire depuis 2016 et comment nous nous situons par rapport à des communes comparables. »

**Sujet retenu :** annexe A, n° 6 – Délinquance enregistrée.

**Question principale :** sur quels types de délits et dans quelles communes de Loire-Atlantique le conseil doit-il concentrer ses actions de prévention ?

## Questions analytiques

1. Quels types de délits ont augmenté ou diminué dans le département depuis 2016 ?
2. Pour quels types de délits le département est-il au-dessus ou en dessous de la région et de la France ?
3. Comparées à des communes de même type (urbaines, périurbaines, rurales), les communes du département enregistrent-elles plus ou moins de faits ?
4. Les faits enregistrés sont-ils concentrés dans quelques communes du département ? (en nombre de faits, avec la part de population)
5. Quelle part des données est publiée à l'échelle des communes, et pour quels délits ?

Le détail (colonnes utilisées, hypothèses) est dans [`docs/questions.md`](docs/questions.md).

## Données

| Élément | Valeur |
|---|---|
| Jeu de données | Bases statistiques communale, départementale et régionale de la délinquance enregistrée par la police et la gendarmerie nationales |
| Producteur | Service statistique ministériel de la sécurité intérieure (SSMSI), ministère de l'Intérieur |
| Licence | Licence Ouverte Etalab 2.0 |
| URL | https://www.data.gouv.fr/datasets/bases-statistiques-communale-departementale-et-regionale-de-la-delinquance-enregistree-par-la-police-et-la-gendarmerie-nationales |
| Date de téléchargement | À compléter |
| Date de dernière mise à jour par le producteur | À compléter |
| Périmètre retenu | Département de la Loire-Atlantique (44), années 2016 à 2025 |
| Référentiel complémentaire | Grille communale de densité, INSEE |

Les données ne sont pas versionnées dans le dépôt. Elles se téléchargent avec le script `src/download.py` (voir ci-dessous).

## Installation

Prérequis : Python 3.11 ou supérieur, et Git.

```bash
git clone https://github.com/kourasoumare/projet1_delinquance_enregistree.git
cd projet1_delinquance_enregistree
python3 -m venv .venv
source .venv/bin/activate        # Windows : .venv\Scripts\activate
pip install -r requirements.txt
```

## Reproduire l'analyse

1. Télécharger les données : `python src/download.py`
2. Exécuter le notebook `notebooks/01_exploration.ipynb`
3. Lancer le tableau de bord : `streamlit run app/dashboard.py`

## Structure du dépôt

```
├── app/            # tableau de bord Streamlit
├── data/
│   ├── raw/        # données brutes (non versionnées)
│   └── processed/  # données nettoyées (non versionnées)
├── docs/           # questions, anomalies, décisions, post-mortem
├── notebooks/      # analyse exploratoire
└── src/            # fonctions de téléchargement, nettoyage et calcul
```

## Résultats principaux

À compléter à la fin de l'analyse (3 à 5 constats, une phrase chacun).

## Limites

- La délinquance enregistrée dépend du taux de dépôt de plainte : elle ne mesure pas la délinquance réelle.
- Certaines valeurs communales ne sont pas diffusées (secret statistique), ce qui peut sous-estimer les taux.
- Les taux des petites communes varient fortement d'une année à l'autre.
- Les données sont annuelles : aucune analyse par mois ou par saison n'est possible.
- Les indicateurs n'ont pas tous la même unité de compte (victimes, infractions, véhicules) et ne peuvent pas être additionnés.

## Équipe

| Membre | Rôle (J3) | Rôle (J4) | GitHub |
|---|---|---|---|
| Koura | Chef de projet | Chef de projet | @kourasoumare |
| Bambi | Responsable dépôt | Responsable restitution | @cissebambi451-eng |
| Mahamane | Responsable données | Responsable dépôt | @Mahamane223 |
| Coumba | Responsable restitution | Responsable données | @Coumbatraore |