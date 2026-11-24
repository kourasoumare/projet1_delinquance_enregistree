# Journal des décisions

Chaque décision structurante de l'équipe est notée ici avec sa justification.
Les décisions de la phase de cadrage sont classées par étape ; les suivantes portent leur date.

## Cadrage

| Décision | Justification |
|---|---|
| Sujet retenu : A.6, délinquance enregistrée | Sujet attribué à l'équipe en S41 |
| Périmètre géographique : département de la Loire-Atlantique (44) | Périmètre conseillé par le cahier des charges (un département). Le département mélange une grande ville (Nantes), du périurbain et du rural, ce qui permet la comparaison de la Q3. Il limite aussi le volume de données. |
| Périmètre temporel : 2016 à 2025 | Toute la période disponible, comme le conseille la fiche du sujet |
| Échelle du département plutôt qu'un EPCI | Plus simple, conforme au périmètre conseillé, sans jointure supplémentaire |
| 5 questions analytiques (voir `docs/questions.md`) | Elles découpent le besoin du commanditaire en questions traitables avec les colonnes de la base |
| Q4 calculée en nombre de faits, avec la part de population à côté | La Q4 cherche où les faits se produisent. La part de population évite de stigmatiser une commune simplement parce qu'elle est grande. La comparaison en taux est traitée dans la Q3. |
| Hypothèses H1 (villes et campagne) et H2 (violences intrafamiliales) | Demandées par le prof (EF-05), vérifiables avec les données disponibles |
| Hypothèse sur les dépôts de plainte transformée en précaution d'interprétation | Le nombre de plaintes n'est pas dans les données : l'hypothèse ne serait pas vérifiable |

## Organisation

| Décision | Justification |
|---|---|
| Rôles en J3 : Koura chef de projet, Bambi responsable dépôt, Mahamane responsable données, Coumba responsable restitution | Rôles imposés par le cahier des charges (section 11) |
| Rotation en J4 : Coumba données, Mahamane dépôt, Bambi restitution | Les rôles changent à chaque semaine école ; le chef de projet reste fixe |
| Répartition du code : Koura Q1 et page d'accueil ; Mahamane téléchargement, nettoyage et Q5 ; Bambi Q2, Q3 et H1 ; Coumba Q4, H2 et vue par commune | Charge de travail équilibrée ; chaque membre porte ses questions de bout en bout et peut les expliquer à la revue de code |

## Décisions datées

| Date | Décision | Justification |
|---|---|---|
| 24/11/2026 | Structure du dépôt conforme à l'annexe B | Structure minimale exigée par le cahier des charges |
| 24/11/2026 | Données exclues du dépôt via `.gitignore` | Exigence GIT-04 : les données brutes ne sont pas versionnées |
| 24/11/2026 | Compléments au cadrage envoyés au prof (question principale, précision sur Q4, hypothèses) | Demandés par le prof pour rendre le cadrage définitif |