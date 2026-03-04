# Dataset used in “Drone-enhanced offshore spare part fulfilment using mobile additive manufacturing factories and multi-modal delivery” 

## Overview

This repository contains the datasets used in the study "“Drone-enhanced offshore spare part fulfilment using mobile additive manufacturing factories and multi-modal delivery” published in the International Journal of Production Research.

> **Associated Paper**
>
> Granados-Rivera, D., Silva, D. F., Smith, A. E., Sgarbossa, F., & Knofius, N. (2025). *Drone-enhanced offshore spare part fulfilment using mobile additive manufacturing factories and multi-modal delivery*. International Journal of Production Research, 1–26. https://doi.org/10.1080/00207543.2025.2540454 

The dataset supports both **numerical experiments** for the matheruistic validation and benchmarks, and the **case study**, enabling the evaluation of different instance sizes, capabilities, number of drones, penalization costs, and demand distributions.

All data are provided in **CSV format** and are organized to facilitate reproducibility of computational experiments and validation of optimization models.

---

## Repository Structure

```
offshore-mam-factories-dataset-main/
│
├── README.md
├── LICENSE
├── CITATION.cff
│
└── data/
    ├── case_study/
    │   ├── demand_distribution_1/
    │   ├── demand_distribution_2/
    │   ├── demand_distribution_3/
    │   └── demand_distribution_4/
    │
    └── numerical_experiments/
        ├── small_instance_1/
        ├── small_instance_2/
        ├── medium_instance_1/
        └── medium_instance_2/
```
Each instance directory contains a complete set of CSV files describing the parameters required to run the optimization model.

## Dataset Description

Each dataset instance includes the following files:

| File | Description |
|-----|-------------|
| `alpha.csv` | Production-related parameters |
| `beta.csv` | Cost parameters |
| `customers.csv` | Customer demand data |
| `eta.csv` | Penalty parameters |
| `harbors.csv` | Harbor characteristics |
| `lambda.csv` | Transportation parameters |
| `locations.csv` | Candidate facility locations |
| `parameters.csv` | General model parameters |
| `theta.csv` | Capacity parameters |

These files collectively define the input data required to solve the optimization problem studied in the research.

---

## Case Study Data

The `case_study` folder contains datasets derived from a real-world inspired scenario.  
Four demand distributions are considered:

- `demand_distribution_1`
- `demand_distribution_2`
- `demand_distribution_3`
- `demand_distribution_4`

Each directory represents a different demand scenario used to evaluate the robustness of the model.

---

## Numerical Experiments

The `numerical_experiments` folder contains synthetic benchmark instances designed to test the scalability and computational performance of the model.

Two instance sizes are provided:

### Small instances
- `small_instance_1`
- `small_instance_2`

### Medium instances
- `medium_instance_1`
- `medium_instance_2`

These datasets allow controlled evaluation of algorithmic performance under different problem sizes.

---

## Data Format

All datasets are provided as **comma-separated values (CSV)** files.

Files can be loaded using most scientific computing tools, including:

- Python (pandas)
- R
- MATLAB
- Julia
- Excel

---

## Reproducibility

The dataset is structured so that each instance folder contains all necessary parameters to reproduce the computational experiments described in the associated article.

Users can select any instance directory and directly load the CSV files as input to their implementation of the model.

---

## License

This dataset is distributed under the terms specified in the `LICENSE` file.

---

## Citation

If you use this dataset in your research, please cite it using the information provided in `CITATION.cff`.

---

## Contact

For questions or issues related to the dataset, please open a GitHub issue in this repository.
