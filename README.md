# china-pm2.5

Time series regression with LSTMs predicting PM2.5 concentration in China.

The following experiment uses the following [dataset](https://archive.ics.uci.edu/ml/datasets/PM2.5+Data+of+Five+Chinese+Cities). This hourly data set contains the PM2.5 data in Beijing, Shanghai, Guangzhou, Chengdu and Shenyang. Meanwhile, meteorological data for each city are also included.

## What is this about?

The goal is to predict the average PM2.5 concentration of all cities across measuring stations for a given day.
One could eigher create one average concentration value per day or have a more detailed regression with exact averages across all stations per hour.
Doing both and comparing them afterwards seems like the best solution.

The library dataprep was used for an easy and intuitive eploratory data analysis and enabled the iterative implementation of a preprocessing function.
Using optuna and mlflow, searching for a good set of hyperparameters produced good results.

## Results

### Daily

- MAE: 0.005021880380809307
- MSE: 3.674683102872223e-05

Target:
![Target daily](/img/target-daily.png)

Prediction:
![Prediction daily](/img/predicted-daily.png)

### Hourly

- MAE: 0.0072510442696511745
- MSE: 8.668927330290899e-05

Target:
![Target hourly](/img/target-hourly.png)

Prediction:
![Prediction hourly](/img/predicted-hourly.png)
