# An Analysis of Police Incident Reports from 2018 to March 2025

Data sourced from [DataSF's Open Data Portal](https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-2018-to-Present/wg3w-h783/about_data) and features over 900k incident reports, both those filed by officers on the scene and by citizens through SF's self service online reporting.
 
### ***"EDA.ipynb"* - Analysis and Visualization**
This notebook is an exploratory analysis of the incident dataset. Dataset size is reduced by removing columns and rows with missing data (chose not to impute missing location data) to about ~860k rows. Incident categories are also cleaned up and unified, to focus on several major incidents including:
- Theft
- Assault
- Vandalism
- Burglary
- Motor Vehicle Theft
- ... and other similar criminal incidents

Several categories were removed from the dataset (dubbed minor incidents) and include:
- Recovered Vehicle
- Accidental, natural, and unknown death reports
- Traffic Collision
- Suspicious Occurences 
- ... 

Size of the final unified dataset with focus on major incidents is ~670k.   

### ***"preprocess.ipynb"* - Preprocessing**
This notebook details my preprocessing pipeline. Categorical columns are either left as is (for tree models) or compressed into latent embeddings via autoencoder. Data is also scaled with MinMaxScalar and StandardScalar.  

### ***"models.ipynb" and "treemodels.ipynb"* - Classification Model Training**
These notebooks detail my model selection, training, and evaluation for classification of incident categories. For the 17-class classification task, I acheived a 1.701 log-loss.   

### ***"forecasting.ipynb""* - Time Series Forecasting of Daily Crime Rates**
This notebook contains my data pipeline to convert this dataset into a time series and engineer features from that series to train a forecasting model. I acheived an RMSE of 24.7 using XGBRegressor.