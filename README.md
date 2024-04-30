# Behavior-driven forecasts of neighborhood-level COVID-19 spread in New York City

Codes for Renquan Zhang, Jilei Tai, Qing Yao, Wan Yang, Kai Ruggeri, Jeffrey Shaman, Sen Pei.  Behavior-driven forecasts of neighborhood-level COVID-19 spread in New York City. Codes were programmed by Jilei Tai (taijilei@mail.dlut.edu.cn).

## System requirements and installation guide

The codes can be run on regular laptops or desktop computers. No installation is required. You can run the codes using any computing platform that supports Python programming. The codes have been tested on Python 3.12.1.

## Demo and instructions for use

### 1. Synthetic disease transmission

Read in the mobility matrix (M.txt), crowding matrix (density.txt), dwell time matrix (dwell.txt) for each category of locations at each UHF, the NYC population data (NYCpop.xlsx)，daily infected person report rate (sim_obs.xlsx), and daily humidity data (NY_humudity.csv). Given the number of days of transmission, the initial number of seeds, and the parameters, syntheic_infection.ipynb was run to generate a file of the daily number of new infections in New York City (NYC_sim_obs.txt) and the weekly number of new confirmed diagnoses at each UHF (uhf_sim_obs.txt) as output.

#### Function:

syntheic_infection.ipynb - Synthesis New York City Disease outbreaks at the UHF-level from March to June in 2020

### 2. Modeling neighborhood-level disease transmission using Markov Monte Carlo methods

Read in the mobility matrix (M.txt), the crowding matrix (density.txt), the dwell time matrix (dwell.txt) for each category of locations at each UHF, the daily rate of reported infections (sim_obs.xlsx), the daily humidity data (NY_humudity.csv), the NYC population data (NYCpop.xlsx), the number of new infections per day in NYC (NYC_sim_obs.txt), and the number of new confirmed diagnoses per week for each UHF (uhf_sim_obs.txt). Given the initial state, initial values of the parameters, feasible range of the parameters, and number of training sessions, MCMC.ipynb was run to output the parameters and the predicted number of infections based on the log-likelihood as an evaluation metric.

#### Function:

MCMC.ipynb - Read in UHF-level infected data , use Markov Monte Carlo method for parameter training

### 3. Description of document contents

density.txt：Weekly Crowding of location category p in neighborhood j

dwell.txt：Weekly dwell time of location category p in neighborhood dict_day2week.txt: Week number corresponding to the date

M.txt：Proportion of population living in neighborhood i and visiting place types p in neighborhood j on a daily basis

NY_humudity.csv: Daily absolute humidity for NYC ,which was derived from North American Land Data Assimilation System data

NYC_sim_obs.txt: Simulation-generated daily number of new infections in New York City

NYCpop.xlsx：New York City Population by UHF

sim_obs.xlsx：Daily detection rate for synthetic simulation

uhf_sim_obs.txt: Simulation-generated weekly number of new confirmed diagnoses at each UHF 

uhf_info.xlsx:Names, Zip Codes, and more for 42 UHFs in New York City
