# Workflow Moderation Code

Notebook pipeline for data cleaning, model training, and workflow-level moderation evaluation under code-mixed inputs.

## Repository contents

- `01_data_cleaning.ipynb` — cleans and prepares the source data for downstream experiments.
- `02_training_pipeline.ipynb` — fine-tunes the English-only model and writes prediction score files for downstream workflow analysis.
- `03_workflow_evaluation_pipeline.ipynb` — loads saved score files and runs threshold tuning, routed moderation evaluation, paired instability analysis, disagreement-based deferral, and confidence-abstention analysis.

## Notebook order

Run the notebooks in this order:

1. `01_data_cleaning.ipynb`
2. `02_training_pipeline.ipynb`
3. `03_workflow_evaluation_pipeline.ipynb`

## Data availability

This repository contains the code and notebook pipeline only. The original raw data and derived experiment files are not redistributed here, including processed splits, prediction CSVs, checkpoints, logs, and other generated outputs.

Users who want to run the notebooks should prepare the expected local input files and folder structure themselves.

## Expected structure

```text
workflow-moderation-code/
├── README.md
├── LICENSE
├── 01_data_cleaning.ipynb
├── 02_training_pipeline.ipynb
├── 03_workflow_evaluation_pipeline.ipynb
├── requirements.txt
├── data/
│   ├── splits/
│   └── predictions/
└── outputs/
    ├── checkpoints/
    ├── predictions/
    ├── metrics/
    └── logs/
```

## Notes

- The training notebook expects prepared split CSV files under `./data`.
- The workflow notebook expects prediction score files under `./data/predictions/` or the configured relative input directory.
- Generated outputs are written locally during execution and are not included in the repository by default.

## Setup

Install dependencies with:

```bash
pip install -r requirements.txt
```

## License

This repository is released under the MIT License. See `LICENSE` for details.
