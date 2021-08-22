
# House Prices - Advanced Regression Techniques

![App Screenshot](https://github.com/bharathngowda/machine_learning_Iowa_house_price_prediction/blob/main/housesbanner.png)

### Table of Contents

1. [Problem Statement](#Problem-Statement)
2. [Data Pre-Processing](#Data-Pre-Processing)
3. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
4. [Feature Engineering](#Feature-Engineering)
5. [Model Training](#Model-Building)
6. [Model Selection](#Model-Selection)
7. [Model Evaluation](#Model-Evaluation)
8. [Dependencies](#Dependencies)
9. [Installation](#Installation)

### Problem Statement

Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

**Quick Start:** [View](https://github.com/bharathngowda/machine_learning_Iowa_house_price_prediction/blob/main/House%20Price%20Prediction.ipynb) a static version of the notebook in the comfort of your own web browser.

### Data Pre-Processing

- Loaded the train and test data
- Checking for null values 
- Imputing null values 
- Outlier detection and treatment using IQR method


### Exploratory Data Analysis

- **Correlation Plot** to determine if there is a linear relationship between the 2 variables and the strength of the relationship
- **Pair Plot**  to see both distribution of single variables and relationships between two variables
- Plots to understand what features ae common in most of the houses and what is the mean price for such features.
- Sale Price and Log of Sale Price Distplot


### Feature Engineering

New features created are - 
* Converted HouseStyle from Categorical to Numerical i.e., 1Story to 1, 2Story to 2 etc...
* Converted ExterQual from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2
* Converted ExterCond from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2
* Converted HeatingQC from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2
* Converted KitchenQual from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2
* Converted GarageCond from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted GarageQual from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted BsmtQual from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted BsmtCond from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted PoolQC from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2
* Converted FireplaceQu from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted BsmtExposure from Categorical to Numerical i.e., Ex=5,Gd=4,Ta=3,Fa=2,Po=1
* Converted CentralAir from Categorical to Numerical i.e., Yes=1,No=0
* Converted GarageYrBlt and YearBuilt from object to int datatype
* Created new feature **'OverallQC'** = (OverallQual+OverallCond)/4
* Created new feature **'ExterQC'** = (ExterQual+ExterCond)/2
* Created new feature **'GarageQC'** = (GarageQual+GarageCond)/2
* Created new feature **'BsmtQC'** = (BsmtQual+BsmtCond)/2
* Created new feature **'totalporch'** = WoodDeckSF+OpenPorchSF+EnclosedPorch+3SsnPorch+ScreenPorch
* Created new feature **'ageofhouse'** = YrSold-YearBuilt
* Created new feature **'ageofgarage'** = YrSold-GarageYrBlt
* Created new feature **'haspool'** is 1 if PoolArea is not 0 otherwise 0
* Created new feature **'hasfireplace'** is 1 if Fireplaces is not 0 otherwise 0
* Created new feature **'hasfence'** is 1 if Fence is not 0 otherwise 0
* Created new feature **'hasgarage'** is 1 if GarageArea is not 0 otherwise 0
* Created new feature **'hasbasement'** is 1 if BsmtFinType1 is not 0 otherwise 0
* Created new feature **'SalePriceLog'**=log(SalePrice)

### Model Training

Models used for the training the dataset are - 

- [Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
- [Lasso](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html)
- [Ridge](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html)
- [DicesionTree Regression](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)

### Model Selection

I have used [r2 score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html) as my scorer and used [k-fold cross-validation](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_val_score.html)
to select the model with highest **'r2 score'**.

### Model Evaluation

I fit the final model on the train data and predicted the survival status for the test data and obtained the below result-

| Metric    | Score    |
| :-------- | :------- |
| Root Mean Squared Logarithmic Error  |0.13364   |

### Dependencies
* [NumPy](http://www.numpy.org/)
* [IPython](http://ipython.org/)
* [Pandas](http://pandas.pydata.org/)
* [SciKit-Learn](http://scikit-learn.org/stable/)
* [SciPy](http://www.scipy.org/)
* [Matplotlib](http://matplotlib.org/)
* [Seaborn](https://seaborn.pydata.org/)

### Installation

To run this notebook interactively:

1. Download this repository in a zip file by clicking on this [link](https://github.com/bharathngowda/machine_learning_Iowa_house_price_prediction/archive/refs/heads/main.zip) or execute this from the terminal:
`git clone https://github.com/bharathngowda/machine_learning_Iowa_house_price_prediction.git`

2. Install [virtualenv](http://virtualenv.readthedocs.org/en/latest/installation.html).
3. Navigate to the directory where you unzipped or cloned the repo and create a virtual environment with `virtualenv env`.
4. Activate the environment with `source env/bin/activate`
5. Install the required dependencies with `pip install -r requirements.txt`.
6. Execute `ipython notebook` from the command line or terminal.
7. Click on `House Price Prediction.ipynb` on the IPython Notebook dasboard and enjoy!
8. When you're done deactivate the virtual environment with `deactivate`.
