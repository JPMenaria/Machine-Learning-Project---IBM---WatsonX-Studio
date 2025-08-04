project snapshot :



📝 Project Overview
This project leverages the AutoAI capabilities of IBM Watson Studio to build and evaluate a machine learning model. The objective is to predict a "Value" based on several demographic and indicator features from the provided dataset. The project automatically generated and tested multiple pipelines, ultimately selecting an XGB Regressor as the top-performing model.



💾 Dataset
The model was trained on the Improved Source of Drinking Water.csv dataset.

Source File: Improved Source of Drinking Water.csv

Target/Label Column: Value (double)

Dataset Columns:
State

Age Group

Sector

Gender

Indicator: Describes the metric, e.g., "Percentage of Persons Who Used Mobile Telephone..."

Value: The numerical value to be predicted.

🤖 AutoAI Experiment & Model Selection
The project utilized an IBM Watson Studio AutoAI experiment to automate the machine learning workflow.

Pipeline Leaderboard
The AutoAI experiment ranked multiple candidate pipelines. Pipeline 5, which uses an XGB Regressor, was identified as the best model based on the (Negative) Root Mean Squared Error evaluation metric, achieving a holdout score of -3.371.

Winning Pipeline (P5)
The relationship map below visualizes the steps taken to build the winning pipeline, including feature transformations and the final model training.

Model Details: P5 - XGB Regressor
Model Name: P5 - XGB Regressor: Improved water source machine learning project

Prediction Type: Regression

Evaluation Metric: Negative Root Mean Squared Error

Feature Importance
The importance of each feature in the final model's predictions is as follows:

Gender: 0.327

NewFeature_0_log(State): 0.267

State: 0.2598

Sector: 0.1262

Age Group: 0.0193

🚀 How to Use
The trained model is saved as a pickle file (P5.pickle) within the project assets. To use it for predictions, you would load this file into a Python environment and provide input data that matches the schema of the training data.

Example Python Snippet:

Python

import pickle

# Load the trained model
# Note: The actual model file is inside the assets/wml_model directory
try:
    with open('path/to/your/assets/wml_model/P5.pickle', 'rb') as f:
        model = pickle.load(f)
except FileNotFoundError:
    print("Model file not found. Please update the path.")
    model = None

if model:
    # Prepare your input data as a pandas DataFrame
    # The columns must match the training data:
    # ['State', 'Age Group', 'Sector', 'Gender', 'Indicator']
    # Example:
    # new_data = pd.DataFrame(...)

    # Make predictions
    # predictions = model.predict(new_data)
    # print(predictions)
    print("Model loaded successfully. Ready for prediction.")

📂 File Manifest
Improved-Source-of-Drinking-Machine-learning-Project.zip: The main project archive.

project.json: Core project metadata.

assets/: Contains all project assets.

data_asset/Improved Source of Drinking Water.csv: The raw dataset used for training.

wml_model/: Contains the serialized model (P5.pickle) and its JSON definition.

.METADATA/: Holds metadata JSON files for the data asset, model, and pipeline.

assettypes/: Defines the schemas for assets used in Watson Studio.

README.md: This informational file.
