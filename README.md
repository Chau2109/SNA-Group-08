# SNA Group 08 Trade Governance Analysis

## Overview
This project examines how similarities in country governance relate to bilateral trade volumes using social network analysis. Trade flows are represented as a weighted network and modeled with MRQAP and GERGM to capture reciprocity, transitivity, and other dependencies.

## Key files
- **Quarto report**: `SNA-Group-08/Report/templateSNA4DSproject/Report Group 08 Quarto.qmd` contains the written submission with project metadata and the narrative analysis. WHen writting the Result section, look at the Template SNA Quarto file for reference how to present the Result properly.
   <br />
- **Data preparation (RMarkdown)**: `SNA-Group-08/Trade Network Data and Code Base/MRQAP.Rmd`, `SNA-Group-08/Trade Network Data and Code Base/ERGM_threshold_90.Rmd`, `SNA-Group-08/Trade Network Data and Code Base/ERGM_threshold_75.Rmd` contains the main Rcode for MRQAP model (Research Question 1) and ERGM models with 2 different threshold (Research Question 2), loads 2018 bilateral trade data alongside World Bank governance and economic indicators, cleans and merges the datasets, and prepares inputs for modeling.
   <br />
- Fitted models are saved within `SNA-Group-08/Report/templateSNA4DSproject/models`, figures are saved within `SNA-Group-08/Report/templateSNA4DSproject/figures`
  

## How to run
1. Open `Trade Network Data and Code Base/Economic_Trade_Data.Rmd` in RStudio (or run via `rmarkdown::render`), run each chunk of code.
2. Open `Report/templateSNA4DSproject/Report Group 08 Quarto.qmd` and render it with Quarto to generate the full report.
## How to load ERGM models
1. Load the model & View MCMC diagnostic: <br />
   ergm <- readRDS("path_to_model.rds") <br />
   ergm <br />
   summary(ergm)
   par(mfrow = c(1, 1), mar = c(4, 4, 2, 1)) # Set plot parameters <br />
   ergm::mcmc.diagnostics(ergm) <br />
   
3. Load the ergm GOF plot: <br />
   ergm_plot <- readRDS("path_to_model_GOF_plot.rds") <br />
   plot(ergm_plot) <br />
 
