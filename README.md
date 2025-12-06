# SNA Group 08 Trade Governance Analysis

## Overview
This project examines how similarities in country governance relate to bilateral trade volumes using social network analysis. Trade flows are represented as a weighted network and modeled with MRQAP and GERGM to capture reciprocity, transitivity, and other dependencies.

## Key files
- **Quarto report**: `Report/templateSNA4DSproject/Report Group 08 Quarto.qmd` contains the written submission with project metadata and the narrative analysis. WHen writting the Result section, look at the Template SNA Quarto file for reference how to present the Result properly.
- **Data preparation (RMarkdown)**: `Trade Network Data and Code Base/Economic_Trade_Data.Rmd` contains the main Rcode, loads 2018 bilateral trade data alongside World Bank governance and economic indicators, cleans and merges the datasets, and prepares inputs for modeling. 

## How to run
1. Open `Trade Network Data and Code Base/Economic_Trade_Data.Rmd` in RStudio (or run via `rmarkdown::render`), run each chunk of code.
2. Open `Report/templateSNA4DSproject/Report Group 08 Quarto.qmd` and render it with Quarto to generate the full report.
## How to load ERGM models
1. Load the model & View MCMC diagnostic: <br />
   ergm <- readRDS("path_to_model.rds") <br />
   ergm <br />
   par(mfrow = c(1, 1), mar = c(4, 4, 2, 1)) # Set plot parameters <br />
   ergm::mcmc.diagnostics(ergm) <br />
   
3. Load the ergm GOF plot: <br />
   ergm_plot <- readRDS("path_to_model_GOF_plot.rds") <br />
   plot(ergm_plot) <br />
 
