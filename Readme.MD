[![DOI](https://zenodo.org/badge/358875830.svg)](https://zenodo.org/badge/latestdoi/358875830)

# Influenza predictions in Vienna (Data Stewardship TU Wien 2021)

# Description
The goal of this experiment was to model the relationship between weather observations and the prevalence of new influenza infections. 
It included reading, preparing and transforming data. 
Subsequently, these data were visualized and used for building a prediction model - we tried to predict influenza infections based on weather conditions.

This project is a part of Data Stewardship course at [TU Wien](https://www.tuwien.at/en/).

## Technologies
We used Python with Jupyter notebook and `scikit-learn` for modeling. Visualization is handled by `seaborn` and `matplotlib`, 
while data manipulation is handled via `pandas`.

# Installation
We will use `conda` package manager. To install conda, follow this [office guide](https://conda.io/projects/conda/en/latest/user-guide/install/index.html).

To install Jupyter Notebook, use:

`conda install -c conda-forge notebook`

Then run all of those commands to install dependencies:

`conda install numpy`

`conda install pandas`

`conda install matplotlib`

`conda install seaborn`

`conda install scikit-learn`

in order to install all the necessary dependencies.

# Usage
It is very important that you set up correct path to the data files. The default placement is in `'./data/influenza/infleunza.csv'` for
influenza data, `'./data/weather/*.csv'` for weather data.

To create your own predictions, please run the validation with `'./data/influenza/influenza_predict.csv''`

To run sample experiment, simply run all of the cells. Also, make sure the random seed is set to 20 in order to reproduce the results.
Sample code for the linear regression:

`
    
    X = data_merged[predictors].values
    y = data_merged[target_column].values
    
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.1, random_state=20)

    lr = LinearRegression()
    lr.fit(X_train, y_train.ravel()) 
    pred_train_lr = lr.predict(X_train)
    
    pred_test_lr = lr.predict(X_test)
    print("RMSE of testing data for Linear Regression:\t",np.sqrt(mean_squared_error(y_test,pred_test_lr))) 
    print("R2 of testing data  for Linear Regression:\t",r2_score(y_test, pred_test_lr))
    
    pred_final_data_lr = lr.predict(data_merged_predict[predictors])
    print("Train:", pred_train_lr)
    print("Test:", pred_test_lr)
    print("Prediction:\n", pred_final_data_lr)
`

# Contributing
Contributions are welcome and much appreciated!

We follow the git-flow process. Please check [this](https://danielkummer.github.io/git-flow-cheatsheet/).

1. Fork the Project
2. Create your Feature Branch
3. `git checkout -b feature/description`
    
4. Commit your Changes

5. Push to the Branch

6. Open a Pull Request

# Credits
To Katalog Grippemeldedienst der Stadt Wien for data about [influenza occurences](https://www.data.gv.at/katalog/dataset/grippemeldedienst-stadt-wien/resource/fa5edf7a-4236-45d4-a81e-c803eb4450fc). 


# License
The code and the produced data is lincenced under CC BY-SA-NC licence (see LICENCE file for further information)