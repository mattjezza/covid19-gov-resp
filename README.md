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
The project is presented as:

- a Jupyter notebook `Effectiveness-of-Government-Responses-to-Coronavirus.ipynb`
- a post on Medium (not yet published, but will appear at https://medium.com/@matt_chap)

Other files in this repository:
- `environment.yml` which defines the conda environment to run the notebook
- this `README.md` file
- Effectiveness-of-Government-Responses-to-Coronavirus.html (HTML version of
the notebook)
- Effectiveness-of-Government-Responses-to-Coronavirus.zip (HTML version of
the notebook with a better table of contents and easier navigation)

The Jupyter notebook is split into sections as follows:

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

The main conclusions are:

1. The level of excess fatalities in a country does have some relationship to both the time when lockdown took place and the time when testing started (the earlier these happen, the greater the chance of a lower level of excess fatalities) but it's clear these are not the only factors that are important.

2. The K-means clustering model tentatively suggests that the following measures are more strongly associated with low excess deaths:
- `C4_Restrictions on gatherings`
- `E1_Income support`
- `time_to_lockdown` (a low value means earlier lockdown)
- `first_week_of_testing` (a low value means starting testing sooner)

compared to the measures:
- `C5_Close public transport`
- `C5_Flag`
- `C6_Stay at home requirements`
- `H3_Contact tracing`

The clustering model gives interesting results but it is limited by the lack of countries with excess deaths data.

3. The regression model predicted reasonably well on any given day ("one day ahead") but the accuracy soon breaks down after more than 5 days. The government measures have such small importance in the model that it's not possible to draw any conclusions about them.

## Requirements
The repository includes a conda environment file.
To set up the environment, run:

`conda env create -f environment.yml`

To activate the environment:

`conda activate cv19-env`

The Jupyter notebook can then be run as-is.

The key conda packages used are:
- python 3
- lightgbm
- scikit-learn
- seaborn
- pandas
- matplotlib
- numpy
- gitpython

This is not a complete list. See `environment.yml` for a full list.

## How to Run the Jupyter Notebook
This notebook requires data from three remote repositories. The notebook checks for the existence of a local copy of each of the three directories independently. The expected directory names are defined in OXFORD_DATA_DIR, OWID_DATA_DIR and ECONOMIST_DATA_DIR, and the expected location is the directory where the notebook is running. If a local directory is not found, then the code will clone the data from the appropriate remote into the local directory with the defined name. Alternatively, if the directory is found then it is assumed to be correct and ready for use, and therefore it will not be cloned or updated. This approach means that the notebook will run with no changes. On the first run, the notebook will download the data for all three repositories automatically. Any subsequent runs of the notebook in the same directory will use the local copy without downloading it again, so it will run more quickly.

If you wish to remove a local copy of the data downloaded previously and clone it again cleanly, or if errors occur (e.g. network loss or other failure) during the clone please delete the directory manually and re-run the notebook.

Training the regression model can take a long time. By default, the notebook will search a small range of parameters using GridSearchCV. This will work with no changes. To adjust the parameters (and affect the training time), see section 6.6. Training the Model. Three sets of parameters are given, two of these are commented out. It is possible to comment the current set and uncomment either the set which does no parameter searching (for quicker training and reasonable performance) or the set which searches a wider range of parameters (which takes longer to train). 

## Data Sources
See the end of notebook `Effectiveness-of-Government-Responses-to-Coronavirus.ipynb` for references and description of the data source.
All data required will be downloaded when the notebook is run for the first
time.

## References and Acknowledgements
See the end of notebook `Effectiveness-of-Government-Responses-to-Coronavirus.ipynb`, which fully lists all references and acknowledgements.
