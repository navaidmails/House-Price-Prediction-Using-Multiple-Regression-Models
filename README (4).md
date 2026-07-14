# House Price Prediction Using Multiple Regression Models

A machine learning web application that predicts house prices using multiple regression algorithms. Users can enter housing and area details, select a trained regression model, generate a price prediction, and compare model evaluation results.

## Project Overview

This project trains and evaluates multiple regression models using the `USA_Housing.csv` dataset. Each trained model is saved as a `.pkl` file and integrated into a Flask-based web application.

The application provides:

- A modern interface for entering property details
- Multiple regression model options
- Instant house-price prediction
- A separate model evaluation page
- Evaluation results saved in CSV format

## Input Features

The prediction is based on the following features:

- Average Area Income
- Average Area House Age
- Average Area Number of Rooms
- Average Area Number of Bedrooms
- Area Population

The `Address` column is removed because it is not used as a numerical input feature.

## Machine Learning Models

The project trains and compares the following models:

1. Linear Regression
2. Huber Regression
3. Ridge Regression
4. Lasso Regression
5. Elastic Net
6. Polynomial Regression
7. SGD Regressor
8. Artificial Neural Network
9. Random Forest Regressor
10. Support Vector Regressor
11. LightGBM Regressor
12. XGBoost Regressor
13. K-Nearest Neighbors Regressor

## Evaluation Metrics

Each model is evaluated using:

### Mean Absolute Error

Measures the average absolute difference between actual and predicted prices.

```text
MAE = Average(|Actual - Predicted|)
```

A lower MAE indicates better performance.

### Mean Squared Error

Measures the average squared difference between actual and predicted prices.

```text
MSE = Average((Actual - Predicted)²)
```

A lower MSE indicates better performance.

### R² Score

Measures how well the model explains variation in house prices.

```text
R² = 1 - (Unexplained Variation / Total Variation)
```

A value closer to `1` indicates better performance.

## Technologies Used

- Python
- Flask
- Pandas
- Scikit-learn
- LightGBM
- XGBoost
- HTML5
- CSS3
- Bootstrap
- Jinja2
- Pickle

## Project Structure

```text
housing-price-prediction/
│
├── app.py
├── model_training.py
├── USA_Housing.csv
├── model_evaluation_results.csv
├── requirements.txt
├── README.md
│
├── models/
│   ├── LinearRegression.pkl
│   ├── RobustRegression.pkl
│   ├── RidgeRegression.pkl
│   ├── LassoRegression.pkl
│   ├── ElasticNet.pkl
│   ├── PolynomialRegression.pkl
│   ├── SGDRegressor.pkl
│   ├── ANN.pkl
│   ├── RandomForest.pkl
│   ├── SVM.pkl
│   ├── LGBM.pkl
│   ├── XGBoost.pkl
│   └── KNN.pkl
│
├── templates/
│   ├── index.html
│   ├── result.html
│   └── results.html
│
└── static/
    └── css/
        └── style.css
```

The exact structure may vary depending on where the saved model files and stylesheet are placed.

## Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd housing-price-prediction
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

#### Windows

```bash
venv\Scripts\activate
```

#### macOS or Linux

```bash
source venv/bin/activate
```

### 4. Install the required libraries

```bash
pip install flask pandas scikit-learn lightgbm xgboost
```

Alternatively, install dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Training the Models

Run the model-training script before starting the web application:

```bash
python model_training.py
```

The script will:

- Load the housing dataset
- Remove unnecessary columns
- Split the dataset into training and testing sets
- Train all regression models
- Generate predictions on test data
- Calculate MAE, MSE, and R²
- Save trained models as `.pkl` files
- Save evaluation results to `model_evaluation_results.csv`

## Running the Application

Start the Flask application:

```bash
python app.py
```

Open the application in your browser:

```text
http://127.0.0.1:5000/
```

## Application Pages

### Home Page

The home page allows users to:

- Enter housing-related input values
- Select a regression model
- Submit the form for prediction

### Prediction Result Page

The result page displays:

- Selected model name
- Predicted house price
- Link to make another prediction
- Link to view model evaluation results

### Model Evaluation Page

The evaluation page displays a comparison table containing:

- Model name
- MAE
- MSE
- R² score

## Flask Routes

| Route | Method | Purpose |
|---|---|---|
| `/` | GET | Displays the prediction form |
| `/predict` | POST | Processes inputs and returns the prediction |
| `/results` | GET | Displays model evaluation results |

## Example Input

```text
Average Area Income: 79545
Average Area House Age: 5.7
Average Area Number of Rooms: 7.1
Average Area Number of Bedrooms: 4.2
Area Population: 32000
Model: RandomForest
```

The application sends these values to the selected trained model and displays the estimated house price.

## Requirements File

A basic `requirements.txt` file may contain:

```text
Flask
pandas
scikit-learn
lightgbm
xgboost
```

Generate the complete dependency list using:

```bash
pip freeze > requirements.txt
```

## Important Notes

- Train the models before running the Flask application.
- Ensure the dataset path is correct.
- Ensure all `.pkl` files are available at the path used in `app.py`.
- Use the same feature order during prediction that was used during training.
- Polynomial Regression uses a pipeline so that polynomial transformation is applied during prediction.
- Model performance may vary depending on preprocessing, hyperparameters, and the train-test split.

## Future Improvements

- Add stronger input validation and error handling
- Display the best-performing model automatically
- Add model-performance charts
- Add feature scaling for distance-based and gradient-based models
- Use cross-validation for more reliable model comparison
- Add hyperparameter tuning
- Deploy the application on Render, Railway, AWS, or Azure
- Add prediction history and downloadable reports

## Disclaimer

The predicted price is an estimate generated by machine learning models. It should not be treated as professional property valuation or financial advice.

## Author

**Your Name**

Machine Learning Regression Project
