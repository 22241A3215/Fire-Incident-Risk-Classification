# Fire-Incident-Risk-Classification
Fire incident risk classification involves categorizing areas or situations based on the likelihood and severity of fire occurrences to prioritize safety measures. This classification helps in resource allocation, emergency response planning, and implementing preventative strategie
Fire Incident Risk Classification

Project Overview

This project implements a decision tree model to classify the risk level of fire incidents (Low, Medium, High) based on various features such as the incident type, fire size, response time, and the number of casualties. The goal is to predict the fire risk level for new incidents, which can be useful for emergency response planning and resource allocation.

Prerequisites

To run this project, you need to have the following R libraries installed:

tidyverse (for data manipulation and visualization)
caret (for machine learning workflows)
rpart (for decision tree modeling)
rpart.plot (for visualizing decision trees)
You can install the required libraries by running the following commands in R:

install.packages(c("tidyverse", "caret", "rpart", "rpart.plot"))
Steps in the Code

Step 1: Load or Simulate Dataset
The code generates a simulated dataset of fire incidents with features like IncidentType (Residential, Commercial, Industrial), FireSize (size of the fire in hectares), ResponseTime (response time in minutes), and NumberOfCasualties. The target variable, RiskLevel, indicates the fire's risk level (Low, Medium, High).

Step 2: Convert Categorical Variables to Factors
The categorical variables (IncidentType and RiskLevel) are converted to factors to ensure they are treated correctly during the modeling process.

Step 3: Split Data into Training and Testing Sets
The dataset is split into two subsets:

Training data (80%): Used to train the decision tree model.
Testing data (20%): Used to evaluate the model's performance.
Step 4: Train a Decision Tree Model
A decision tree model is trained using the rpart function to predict RiskLevel based on the features IncidentType, FireSize, ResponseTime, and NumberOfCasualties.

Step 5: Visualize the Decision Tree
The trained decision tree is visualized using the rpart.plot() function, which provides a graphical representation of how the model makes its decisions.

Step 6: Evaluate the Model on the Test Data
The model's performance is evaluated on the test data using a confusion matrix to compare the predicted risk levels with the actual values.

Step 7: Save the Trained Model (Optional)
The trained model is saved to a file (fire_risk_model.rds) so it can be loaded and used for future predictions without retraining.

Step 8: Load the Model (if Needed)
If you have a saved model, you can load it using the readRDS() function.

Step 9: Predict Risk Levels for New Data
New fire incident data (e.g., fire size, response time, casualties) is used to predict the risk level using the trained model. The predictions are then added to the new data.

Running the Code

Prepare the Data: The dataset is simulated automatically, so no external dataset is required. However, if you have real fire incident data, you can replace the simulated dataset with your own data.
Train the Model: The rpart function is used to train the decision tree. The model will be based on the features specified in the code (IncidentType, FireSize, ResponseTime, NumberOfCasualties).
Evaluate the Model: After training, the model is tested on unseen data (test set) to evaluate its accuracy using a confusion matrix.
Make Predictions: You can predict the risk levels of new fire incidents by creating a new data frame with incident details and using the trained model to classify them.
Example Output

Confusion Matrix
A confusion matrix will show the accuracy of the model's predictions, i.e., how well it predicted the risk level compared to the actual values in the test data.

Predicted Risk for New Data
For the new incident data, the predicted risk levels will be displayed alongside the input features. For example:

  IncidentType FireSize ResponseTime NumberOfCasualties PredictedRisk
1   Residential      2.5            15                  1           Low
2   Commercial      7.8            10                  3          High
Saving and Loading Models

The trained decision tree model is saved using the saveRDS() function, so it can be loaded later for making predictions without retraining:

saveRDS(model, "fire_risk_model.rds")
# To load the model:
model <- readRDS("fire_risk_model.rds")
License

This project is free to use and modify under the MIT License. If you use it in any research or application, please cite the original work.
