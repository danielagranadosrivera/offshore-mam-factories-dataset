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

Each instance directory contains a complete set of CSV files describing the parameters required to run the optimization model and the heuristics.

---

## Dataset Description

Each dataset instance includes the following files:

| File | Description |
|-----|-------------|
| `alpha.csv` | Cross-sectional area of each part in squared millimetres. Each row corresponds to a part. This file contains a header. |
| `beta.csv` | Binary parameter representing the availability of ships to sail from each harbour to each customer at each day. Each row has a combination and the column "Availability" shows the zero or one. This file contains a header. |
| `customers.csv` | Coordinates of each offshore customer location considered in the instance. Each row has a location. "X" corresponds to the longitude and "Y" corresponds to the latitute. This file has a header. Locations recovered from [The Ministry of Petroleum and Energy – Oil and Gas (2018)](https://www.regjeringen.no/en/topics/energy/oil-and-gas/id1003/). |
| `eta.csv` | Weight of each part in kilograms. Each row corresponds to a part. This file contains a header. |
| `harbors.csv` | Coordinates of each harbor location considered in the instance. Each row has a location. "X" corresponds to the longitude and "Y" corresponds to the latitute. This file has a header. |
| `lambda.csv` | Demand for each part for each customer in each day. Each row has a combination and the column "Value" has the number of units required. This file contains a header. |
| `locations.csv` | Coordinates of each potentital location for the mobile additive manufactoring (MAM) factories considered in the instance. Each row has a location. "X" corresponds to the longitude and "Y" corresponds to the latitute. This file has a header. |
| `parameters.csv` | This is a collection of different inputs required for each instance. The definition of each row is defined below. This file has a header.|
| `theta.csv` | Binary matrix indicating if each MAM factory has the capability of producing each part. Columns represent each part and rows correspond to each factory. This file has a header. |

These files collectively define the input data required to solve the optimization problem studied in the research.

## Parameters.csv content
This file collects several parameter required for each instance. Each row has the name of the parameter in column A and the value in column B. The definitions are:

- *Number of drones*: As the name indicates, it is the name of drones available for the instance to run.
- *Periods*: Total number of periods in the planning horizon of the instance. 
- *CR_f*: Fixed relocation cost for moving a MAM factory in US dollars.
- *CR_v*: Variable relocation cost per kilometre for moving a MAM factory in US dollars.
- *CP_f*: Set-up cost to produce per cross-sectional area of a part at any MAM factory in any day in US dollars.
- *CT*: Transport cost per kilometer for shipping by drone in US dollars.
- *CT1*: Transport cost per kilometer for shipping by land (truck) in US dollars.
- *CT2*: Fixed handling cost for shipping by ship in any period in US dollars.
- *CT3*: Transport cost per unit for shipping by drones in US dollars.
- *CT4*: Transport cost per unit for shipping by land (truck) in US dollars.
- *V_average*: Average speed of moving when a MAM factory is being relocated in kilometres per hour.
- *r_estimation*: Set-up time in the new location when relocating a MAM factory in hours.
- *M*: Sufficiently large number.
- *MA*: Maximum cross-sectional area available for batching in a build in squared millimetres.
- *tau*: Weight capacity of a drone in kilograms.
- *gamma*: Flying speed of drones in kilometres per hour.
- *MT*: Maximum allowed drone route time per day in hours.
- *delta*: Maximum distance a drone can travel without swapping battery in kilometers. Based on drones developed by [NU Flight Services (2020)](https://www.nordicunmanned.com/solutions#cargo) and [Skyports Drone Services (2023)](https://skyportsdroneservices.com/delivery).
- *Speed ship*: Speed of ships in knots.
- *Demand days*: Number of days with due dates to schedule in the descomposition of the second stage. Parameter used for the proposed matheuristic for the rolling horizon.
- *Overlap_final*: Number of days to overlap in the rolling horizon. Parameter used for the proposed matheuristic.
- *Rolling horizon*: Number of days without demand in the descomposition of the planning horizon for the matheuristic. This days are considered without demand.
- *Overlap_ini*: Number of days to overlap in the rolling horizon for the warmup of the matheuristic.
- *CB*: Base cost for the quadratic penalty that depends on the number of unit late and the number of days.

---

## Case Study Data

The `case_study` folder contains datasets derived from a real-world inspired scenario. 
Four demand distributions are considered:

- `demand_distribution_1`
- `demand_distribution_2`
- `demand_distribution_3`
- `demand_distribution_4`

Each directory represents a different demand scenario used to evaluate the robustness of the model. The demand distributions are generated by randomly dividing the 400 total demand by parts, then by customers, and finally by days.

---

## Numerical Experiments

The `numerical_experiments` folder contains synthetic benchmark instances designed to test the scalability and computational performance of the model and the performance of the matheuristic.

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

The dataset is structured so that each instance folder contains all necessary parameters to reproduce the computational experiments described in the associated [article](https://doi.org/10.1080/00207543.2025.2540454).

Users can select any instance directory and directly load the CSV files as input to their implementation of the model.

---

## License

This dataset is distributed under the terms specified in the `LICENSE` file.

---

## Citation

If you use this dataset in your research, please cite it using the information provided in `CITATION.cff`.

---

## Contact

For questions or issues related to the dataset, please open a GitHub issue in this repository. For my information about the research, please refer to the [article](https://doi.org/10.1080/00207543.2025.2540454).
