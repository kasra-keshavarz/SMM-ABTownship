# SMM-ABTownship
Township meteorological data for IJC SMM Study. 

# Workflow
The workflow to caluclate the aerial average daily meteorological values for Alberta Townships is located in the [data-processing](./data-processing.ipynb) Jupyter Notebook.

Please note that the Jupyter Notebook may not be entirely reproducible, as it is currently dependant on the dataset being available locally.

# Results
The results of the process is located in the [./results/IDM_data](./results/IDM_data) directory of the current repository.

> [!CAUTION]
> Previously (commit [1f159c8](https://github.com/kasra-keshavarz/SMM-ABTownship/commit/1f159c87834ae10c7aed613a647dae1122686bfa)), an **INCORRECT** precipitation variable from the `RDRSv2.1` dataset was reported. Specifically, the `RDRS_v2.1_P_PR0_SFC` variable, that is the "model forecasted precipitation" variable. This variable is the background field used by `CaPA` to produce the analysis precipitation values, and should **NOT** have been employed to generate the input data for the `IDM`.

> [!CAUTION]
> In this revision (commit [0aac97f](https://github.com/kasra-keshavarz/SMM-ABTownship/commit/0aac97f46dd42a3aa5705a21be0021b6cb109650) onward), the **CORRECT** `RDRS_v2.1_A_PR0_SFC` precipitation variable is employed to generate the `IDM` input files.

> [!NOTE]  
> Prabin Rokaya, Anil Gupta, and Tom Tang have highlighted the issue with the previously reported township data (commit [1f159c8](https://github.com/kasra-keshavarz/SMM-ABTownship/commit/1f159c87834ae10c7aed613a647dae1122686bfa)), whose care and notes are greatly acknowledged.

> [!IMPORTANT]
> The results generated using the **incorrect** `RDRS_v2.1_P_PR0_SFC` precipitation variable from the `RDRSv2.1` dataset is still archived in this repository under [./results/archive/IDM_data-reforecast-precipitation](./results/archive/IDM_data-reforecast-precipitation) for future reference. The **correct** dataset generated using the appropriate `RDRS_v2.1_A_PR0_SFC` precipitation variable is available for the public under [./results/IDM_data](./results/IDM_data).

An ESRI Shapefile of the Alberta Townships of interest is available under [./results/township_Shapefiles](./results/township_Shapefiles). The workflow to generate this Shapefile is part of the [data-processing](./data-processing.ipynb) Notebook.

# Timezone
The timezone of the data has been set to `MST` America/Edmonton local timezone. The original `RDRSv2.1` data timezone is in UTC.
