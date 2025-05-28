# CS-422-Course-Project
Project Title: Box Office Prediction and Analysis Based on Multi-Dimensional Features (Supervised Learning Regression Problem)


1. Problem Background
The film industry faces high investment risks, with box office performance influenced by multiple factors. This project builds a prediction model based on historical data of 5,000 movies (including budget, cast, director, genre, etc.) to assist investment decisions and quantitatively analyze the impact of various factors on box office revenue.


2. Multi-Dimensional Feature-Based Movie Box Office Prediction and Analysis
This project constructs a regression model system for predicting movie box office revenue (revenue) using the TMDB 5000 Movies Dataset. The system integrates data cleaning, feature engineering, model training and evaluation, and visual analysis, leveraging modern machine learning algorithms to improve prediction accuracy.


3.Project Structure
├── data/                # Raw and processed datasets  
│ └── tmdb_5000_movies.csv  
├── notebooks/           
│ └── box_office_prediction.ipynb  # Main project analysis notebook  
├── outputs/             
│ └── figures/           # Visualization charts (e.g., SHAP, feature importance plots)  
├── README.md            # Project documentation  
├── requirements.txt     # Python dependencies  


4. Technology Stack
Language: Python 3.11
Data Processing: Pandas, NumPy
Visualization: Matplotlib, Seaborn
Machine Learning: Scikit-learn, XGBoost, LightGBM, SHAP
Development Environment: Jupyter Notebook


5. Dataset Introduction
The dataset is sourced from the [TMDB 5000 Movie Dataset] on Kaggle 
(https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata), 
containing metadata such as movie budgets, languages, cast, directors, and genres.
budget: Production budget
genres: Genres (JSON format)
cast, crew: Lists of actors and crew members (JSON)
release_date: Release date
revenue: Box office revenue (prediction target)


6. Project Workflow
(1) Data Cleaning and Preprocessing
Handling missing values, type conversion, and outlier detection;
Decoding and expanding multi-column JSON data (e.g., genres, cast, crew);
Constructing derived variables such as director's average rating and lead actor influence.
(2) Feature Engineering
Processing numerical and categorical variables;
One-Hot encoding and standardization;
Extracting temporal and textual features (e.g., release year, movie name length).
(3) Modeling and Evaluation
Comparison of multiple models: Random Forest, Gradient Boosting, SVR, XGBoost, LightGBM;
Model evaluation metrics: MAE, MSE, RMSE, R²;
Using SHAP for model interpretability analysis.
(4) Results and Visualization
Display of box office prediction performance;
Feature importance ranking and impact plots;
SHAP Beeswarm plots to visualize model decision paths.


7. Model Performance (Example)
Model	MAE 	 MSE	RMSE 	R²
LightGBM	2.13M	9.10e+12	3.01M	 0.84
XGBoost	2.21M	9.56e+12	3.09M	0.82
Random Forest	2.58M	1.14e+13	3.37M	0.79

(Note: Box office units are USD, and performance values are for illustration only)
Optimal Model (LightGBM) Prediction Accuracy:
Error Range: Average deviation of approximately ±18% (log-transformed RMSE = 0.18).
Interpretability: SHAP analysis shows that 10 key features such as budget and director's historical performance contribute 90% of the predictive power.


8. Usage Instructions
(1) Install Dependencies:
pip install -r requirements.txt
(2)Run Notebook:
jupyter notebook notebooks/box_office_prediction.ipynb


9.TODO
Model hyperparameter tuning (GridSearchCV/Optuna)
Introduction of deep learning models (e.g., TabNet, MLP)
Automation pipeline (e.g., using MLflow, Airflow)
Data version control and GitHub Actions integration


10. Key Findings
(1) Core Influencing Factors
Budget: Most critical but non-linearly correlated; optimal return in the range of 50–150 million USD
Talent Effect: Director's historical box office (+38% impact) > lead actor influence (+29% impact)
Genre Differences: Action/adventure genres have a 12% box office premium; documentaries are on average 8% lower
Release Period Dividend: Summer/Christmas 档期 (seasons) boost box office by 15–20%
(2) Investment Strategies
Big Budget Productions: Prioritize action genres + renowned directors + summer 档期
Mid-Small Budget Films: Choose horror/comedy genres + differentiated release periods
Risk Control: Avoid projects with budgets exceeding $200M and niche genres like documentaries


11. Improvement Directions
Data Level: Supplement with operational data such as promotion costs and number of screening theaters
Model Level: Incorporate dynamic market environment factors (e.g., competing films in the same period)
Application Level: Develop customized prediction sub-models by genre/release period

