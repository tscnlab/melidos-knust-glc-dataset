# MeLiDos KNUST GLC dataset

This repository contains the Kumasi, Ghana site data collected by Kwame
Nkrumah University of Science and Technology (KNUST) for the MeLiDos field
study. It is a GLC Schema 3.0.2 Data Package derived from the
[original MeLiDos dataset](https://github.com/MeLiDosProject/AkuffoEtAl_Dataset_2025).

The package entry point is `datapackage.json`. Core study, participant,
device, datasheet, dataset, and variable metadata are stored in `data/`.
Participant-level CSV files referenced by `data/datasets.json` are organized
as:

- `data/files/sensor/`: participant-level head, chest, and wrist sensor tables;
- `data/files/longitudinal-reports/`: diaries, experience and wear logs, and
  repeated assessments;
- `data/files/questionnaires/`: screening, baseline, and end-of-study
  questionnaires;
- `data/files/study-timing/`: participant trial-period records.

The source dataset is:

> Akuffo, K. O., Agbeshie, G. K., Zauner, J., & Spitschan, M. (2025).
> *Personal light exposure dataset for Kumasi, Ghana* (Version 1.0.1)
> [Data set]. https://doi.org/10.5281/zenodo.15576731

The refactoring converts the imported tabular RData resources to UTF-8 CSV,
separates records by participant, and supplies GLC 3.0.2 metadata without
modifying the source repository.

## Validation

The complete package passes GLC Schema 3.0.2 validation with validator 0.5.2.
Validation reports 0 errors. Its warnings identify empty cells already present
in the source tables, including gaps in some sensor streams.

Validation also runs automatically through
`.github/workflows/validate-glc-dataset.yml`. Successful runs produce an
attested `validation-report` artifact containing `validation.json` and
`validated-files-manifest.json`.

## License

The dataset is licensed under the Creative Commons Attribution 4.0
International License (CC BY 4.0). See `LICENSE`.
