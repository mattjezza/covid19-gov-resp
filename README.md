# Exploring COVID-19 Mitigation Strategies with Data Science

## Introduction
This is a data science project to explore the strategies used by
governments around the world to stop the spread of COVID-19 and minimise
fatalities. There is already good evidence that these strategies have saved
many lives (see the notebook reference [17] about this)
but the question that is really fascinating and potentially useful is:

**Which measures are most effective in preventing the spread of the virus and
saving lives?**

That is the main aim and motivation of this project.

## Content Summary
The project is presented as a Jupyter notebook and an associated post on
Medium (not yet published, but will appear at https://medium.com/@matt_chap).

The project is split into sections as follows:

**1. Introduction**
- The background and aims of the project.

**2. Data Understanding**
- Data sources
- Data download
- Initial data exploration

**3. Data Preparation**
- Data cleaning
- Merging data sources
- Feature engineering

**4. Analysis and Visualisation**
- Comparing the impact of the virus on different countries
- Relating the impact of the virus to government measures over time
- Speed of government responses
- Effect of testing

**5. Clustering model based on government measures and excess fatalities**
 - Using K-means clustering to find which measures lead to lower excess deaths

**6. Prediction model for confirmed cases**
- Using a regression model to predict the number of new cases on a date
- Using the model to predict new cases as a time series
- Analysing the feature importance in the model

**7. Conclusions**

## Requirements
The repository includes a conda environment file.
To set up the environment, run:

`conda env create -f environment.yml`

To activate the environment:

`conda activate cv19-env`

The notebook can then be run as-is.

The key conda packages used are:
- python 3
- lightgbm
- scikit-learn
- seaborn
- pandas
- matplotlib
- numpy
- gitpython

This is not a complete list. See environment.yml for a full list.

## Data Sources
See the notebook for references and description of the data source.
All data required will be downloaded when the notebook is run for the first
time.

## References and Acknowledgements
See the notebook, which fully lists all references and acknowledgements.
