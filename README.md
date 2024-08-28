# Football Player Talent Predictor 🌟⚽

![scoutium](https://github.com/user-attachments/assets/b3582d82-9baa-4adf-a32b-918f781173c4)

## Overview
This project analyzes football player data to predict player categories (e.g., "average", "standout") based on evaluations provided by scouts. By leveraging various machine learning models, including CatBoost, the project aims to determine which players have the potential to excel. 

## Dataset
The dataset is sourced from Kaggle.
The dataset contains ratings given by scouts based on the characteristics of football players. It is composed of two CSV files:
- **scoutium_attributes.csv**: Contains the attributes rated by scouts for each player.
- **scoutium_potential_labels.csv**: Contains the final decision labels for each player (the target variable).

### Features
- **task_response_id**: ID for a set of evaluations by a scout for all players in a match.
- **match_id**: Unique ID of the relevant match.
- **evaluator_id**: Unique ID of the scout.
- **player_id**: Unique ID of the player.
- **position_id**: ID representing the player’s position (e.g., 1: Goalkeeper, 2: Defender).
- **analysis_id**: ID for a set of a scout's evaluations.
- **attribute_id**: ID for each attribute evaluated.
- **attribute_value**: Value (rating) given by the scout for an attribute.
- **potential_label**: The final decision label given by the scout (target variable).

## Project Workflow

### 1. Data Preprocessing
- Merging datasets and filtering out irrelevant data 
- Removing players labeled as "below_average" 
- Creating a pivot table to aggregate player attributes by `player_id`, `position_id`, and `potential_label`.
- Generating additional features such as `min`, `max`, `sum`, `mean`, and `median` of the attribute ratings.

### 2. Feature Engineering
- Introduced a new feature `mentality`, categorizing players as either "defender" or "attacker" based on their position.
- Applied one-hot encoding to categorical variables such as `position_id`.
- Scaled numerical features to ensure all attributes contribute equally to the model.

### 3. Model Training and Evaluation
- Split the dataset into training, validation, and test sets.
- Applied various machine learning models including Logistic Regression, KNN, SVM, Decision Trees, Random Forest, AdaBoost, Gradient Boosting, XGBoost, and CatBoost.
- Evaluated models using metrics such as ROC AUC, F1 score, Precision, Recall, and Accuracy.
- Tuned hyperparameters for the CatBoost model using GridSearchCV to optimize performance.

### 4. Final Model Testing
- Tested the final model using the best-found parameters on the test set and evaluated its performance.

## Results
The CatBoost model was found to perform best, achieving the highest ROC AUC score during the model evaluation process. The model effectively predicts which players are likely to stand out based on the attributes provided by scouts.

## How to Run
1. Clone this repository: git clone https://github.com/yourusername/FootballPlayerTalentPredictor-.git
2. Install the necessary dependencies using:
   ```bash
   pip install -r requirements.txt
