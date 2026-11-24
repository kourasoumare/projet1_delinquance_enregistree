# Questions analytiques

**Sujet :** A.6 – Délinquance enregistrée
**Périmètre :** département de la Loire-Atlantique (44), 2016 à 2025
**Source :** base communale de la délinquance enregistrée (SSMSI), complétée par la grille communale de densité (INSEE)
**Statut :** périmètre et questions validés par le commanditaire ; compléments envoyés, en attente de validation définitive

## Question principale

Sur quels types de délits et dans quelles communes de Loire-Atlantique le conseil doit-il concentrer ses actions de prévention ?

## Questions analytiques

### Q1. Quels types de délits ont augmenté ou diminué dans le département depuis 2016 ?

- **Colonnes :** `annee`, `indicateur`, `unite_de_compte`, `nombre`
- **Méthode :** somme des faits par indicateur et par année, puis évolution en base 100 en 2016. Comparaison des périodes 2016-2019 et 2021-2025, l'année 2020 (confinements) étant traitée à part.
- **Règle :** on n'additionne jamais deux indicateurs, car leurs unités de compte diffèrent (victimes, infractions, véhicules).
- **Responsable :** Koura

### Q2. Pour quels types de délits le département est-il au-dessus ou en dessous de la région et de la France ?

- **Colonnes :** `nombre`, `insee_pop`, `insee_log`, code commune ; bases départementale, régionale et nationale du SSMSI
- **Méthode :** taux du département = somme des faits ÷ somme de la population × 1 000 (logements pour les cambriolages). Comparaison aux taux régional et national, puis classement des délits par écart avec la France.
- **Règle :** taux calculé à partir des sommes, jamais comme moyenne des taux communaux.
- **Responsable :** Bambi

### Q3. Comparées à des communes de même type (urbaines, périurbaines, rurales), les communes du département enregistrent-elles plus ou moins de faits ?

- **Colonnes :** `taux_pour_mille`, code commune
- **Jointure :** grille communale de densité INSEE (EF-06)
- **Méthode :** taux médian par niveau de densité, en Loire-Atlantique et en France.
- **Règle :** médiane plutôt que moyenne, car les taux des petites communes sont très instables.
- **Responsable :** Bambi

### Q4. Les faits enregistrés sont-ils concentrés dans quelques communes du département ?

- **Colonnes :** `nombre`, `insee_pop`, code commune, `annee`, `indicateur`
- **Méthode :** part des faits portée par les 3 à 5 premières communes, chaque année, en nombre de faits. La part de population de ces communes est affichée à côté.
- **Règle :** tout classement de communes est accompagné de ses limites, pour ne stigmatiser aucun territoire.
- **Responsable :** Coumba

### Q5. Quelle part des données est publiée à l'échelle des communes, et pour quels délits ?

- **Colonnes :** `est_diffuse`, `indicateur`, `annee`
- **Méthode :** part des valeurs non diffusées par indicateur et par année.
- **Règle :** un « 0 » n'est publié que si aucun fait n'est enregistré pendant 3 années de suite : il est à lire avec précaution.
- **Responsable :** Mahamane

## Hypothèses (formulées avant tout calcul)

- **H1.** Pour chaque type de délit, le taux pour 1 000 habitants est plus élevé dans les communes urbaines que dans les communes rurales du département. *Vérifiée avec la Q3.*
- **H2.** Entre 2016 et 2025, les violences physiques intrafamiliales enregistrées ont augmenté plus fortement que les autres types de délits. *Vérifiée avec la Q1.* Si elle se confirme, une partie de la hausse peut venir de l'augmentation des dépôts de plainte, et pas seulement d'une hausse réelle des violences.

## Limites connues dès le cadrage

- La délinquance enregistrée dépend du taux de dépôt de plainte : elle ne mesure pas la délinquance réelle.
- Certaines valeurs communales ne sont pas diffusées (secret statistique).
- Les taux des petites communes varient fortement d'une année à l'autre.
- Les données sont annuelles : aucune analyse par mois ou par saison n'est possible.
- Les noms exacts des colonnes et des indicateurs sont à vérifier au premier chargement des données.