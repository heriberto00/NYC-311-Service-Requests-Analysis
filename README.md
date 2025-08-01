# Capstone Project: NYC-311 Service Requests Analysis.

### Project Overview.
A NYC-311 service request is a request for the City to provide assistance, perform an inspection, or address a problem. NYC-311 is a public service with the intent of expanding access to resources, but is this access expanded equally? By analysing over 2 million service requests and measures like poverty rate and racial diversity index, I want to find the relationship between resolution times and demographic indicators, to see if these are somehow predictors for how quick a service request will be solved.

## Dataset.
The main dataset I will be using is the ["311 Service Requests from 2010 to Present"](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data) dataset from NYC OpenData. This dataset contains all 311 Service Requests from 2010 to present, and it's updated daily. Additional datasets used are the [racial diversity index](https://app.coredata.nyc/?mlb=false&ntii=pop_race_div_idx&ntr=Sub-Borough%20Area&mz=14&vtl=https%3A%2F%2Fthefurmancenter.carto.com%2Fu%2Fnyufc%2Fapi%2Fv2%2Fviz%2F98d1f16e-95fd-4e52-a2b1-b7abaf634828%2Fviz.json&mln=true&mlp=false&mlat=40.729123&nty=2021&mb=roadmap&pf=%7B%22subsidies%22%3Atrue%7D&md=table&mlv=false&mlng=-73.992714&btl=Borough&atp=neighborhoods) and [poverty rate](https://app.coredata.nyc/?mlb=false&ntii=pop_pov_pct&ntr=Sub-Borough%20Area&mz=14&vtl=https%3A%2F%2Fthefurmancenter.carto.com%2Fu%2Fnyufc%2Fapi%2Fv2%2Fviz%2F98d1f16e-95fd-4e52-a2b1-b7abaf634828%2Fviz.json&mln=true&mlp=false&mlat=40.729123&nty=2021&mb=roadmap&pf=%7B%22subsidies%22%3Atrue%7D&md=table&mlv=false&mlng=-73.992714&btl=Borough&atp=neighborhoods) distributions from NYU's Furman Center, [median household income](https://simplemaps.com/city/new-york/zips/income-household-median) distribution by ZIP code from simplemaps, and the ["NYC Community Boards"](https://data.cityofnewyork.us/City-Government/NYC-Community-Boards/ruf7-3wgc/about_data) dataset from NYC OpenData. Columns from these datasets will be used to get a better picture of the location where the 311 requests where made from and extract valuable indicators related to the request's resolution time, if any. 

Feature overviews for all datasets are available [here](https://github.com/heriberto00/NYC-311-Service-Requests-Analysis/tree/main/data/datasets).

## Workflow.

### [Data Cleaning.](https://github.com/heriberto00/NYC-311-Service-Requests-Analysis/blob/main/data/notebooks/Data%20Cleaning.ipynb)
See overview of each dataset used [here](https://github.com/heriberto00/NYC-311-Service-Requests-Analysis/tree/main/data/datasets). Our processed dataset contains 14 columns, including request information such as created date and agency responsible for the resolution, geographic data such as borough and community board where the request was originated, and demographic data such as poverty rate, racial diversity and median income. 

### [Exploratory Data Analysis (EDA).](https://github.com/heriberto00/NYC-311-Service-Requests-Analysis/blob/main/data/notebooks/EDA.ipynb)
Thorough analysis and visualization done allowed to inspect the distribution of requests on each borough, the average resolution time of requests by each city agency, and the frequency of each complaint type.

### [Modeling.](https://github.com/heriberto00/NYC-311-Service-Requests-Analysis/blob/main/data/notebooks/Modeling.ipynb)
The purpose of the regression model trained is to predict the time until a 311 service request is resolved. 

Models trained and tested: linear regression, decision tree regression, XGBoost regression. XGBoost regression was chosen as the final model.


## Findings and future work.
The best performing model was able to explain 26% of the variance in the data. 

Future work to improve the model's performance can be: including more relevant features like additional demographic data, better encoding of relevant categorical variables, and addressing the imbalanced distribution of our target variable.
