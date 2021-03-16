# conformalized_survival_analysis_paper
This repository contains the code to reproduce the numerical results in the [Conformalized Survival Analysis]() paper. 

## Overview
We implement the CQR- and CDR-LPB from scratch to reproduce the numerical results in Section 4 of the paper. We do not include the code for the results in Section 5 because the UK Biobank data is only available to registered users; see https://www.ukbiobank.ac.uk/ for details.

Based on the code, we further develop an R package `cfsurvival` that implements the procedure. The package will be constantly improved and udpated. We recommend the users download the R package to apply our procedure.

## Folders
- `R/`: contains the main functions that implement the CQR, CDR, and other competing methods considered in Section 4.
- `utils/`: contains the helpers for the experiments. 
- `simulation/`: contains the scripts to carry out the simulations.
- `results/`: stores the simulation results.
- `bash/`: bash files to run the simulations in batch mode.

## Usage
### Single run
Each script in the `simulation/` folder implements one run of the simulation. The users can specify the random seed when running the script. 
For example, to implement one run of the low-dimensional-homoscedastic-noise experiment in Section 4 with random seed 1, run the following command in your terminal:
```{r}
cd simulation
Rscript ld_homosc.R 1
```

### Multiple runs
The results presented in the paper are based on 100 independent samples. The user can use the bash file in `bash/` to automatically run the whole simulation in batch mode:
```{r}
cd bash
bash run_all.sh
```
It may take a long time if it is run on a laptop. 
