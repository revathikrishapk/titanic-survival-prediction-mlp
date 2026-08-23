# Titanic Survival Prediction using Neural Networks

This project is about predicting whether a passenger survived the Titanic disaster using machine learning and a neural network.

I worked with the Titanic dataset and built a complete machine learning workflow, starting from data cleaning and preprocessing to model training, experimentation, and final evaluation.

## What I did

The dataset was first explored to understand its structure and identify missing values.

The main preprocessing steps included:

- Handling missing values in `Age` using the median
- Handling missing values in `Embarked` using the mode
- Removing `Cabin` because most of its values were missing
- Selecting relevant features for prediction
- Encoding categorical features such as `Sex` and `Embarked`
- Scaling numerical features using `StandardScaler`
- Splitting the data into training, validation, and test sets

The final dataset contained 623 training samples, 134 validation samples, and 134 test samples.

## Models

### Logistic Regression

I first used Logistic Regression as a baseline. This helped me compare the neural network with a simpler machine learning model.

Validation results:

| Metric | Score |
|---|---|
| Accuracy | 85.82% |
| Precision | 85.11% |
| Recall | 76.92% |
| F1 Score | 80.81% |

### Neural Network

The main model is a Feed Forward Neural Network with two hidden layers.

The architecture uses:

- 8 input features
- First hidden layer with 32 neurons and ReLU activation
- Second hidden layer with 16 neurons and ReLU activation
- One output neuron with Sigmoid activation

The model was trained using:

- Adam optimizer
- Binary Crossentropy loss
- Batch size of 32
- Maximum of 100 epochs
- Early Stopping based on validation loss

Validation results:

| Metric | Score |
|---|---|
| Accuracy | 87.31% |
| Precision | 92.68% |
| Recall | 73.08% |
| F1 Score | 81.72% |

The neural network performed better than Logistic Regression in terms of accuracy, precision, and F1 score.

## Dropout Experiment

I also tested a second version of the neural network by adding Dropout layers.

The purpose was to check whether regularization would improve the model's performance and generalization.

The Dropout model produced the same validation results as the original model:

| Metric | Score |
|---|---|
| Accuracy | 87.31% |
| Precision | 92.68% |
| Recall | 73.08% |
| F1 Score | 81.72% |

Since Dropout did not improve the results, I selected the original MLP as the final model because it was simpler.

## Model Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Logistic Regression | 85.82% | 85.11% | 76.92% | 80.81% |
| Original MLP | 87.31% | 92.68% | 73.08% | 81.72% |
| MLP with Dropout | 87.31% | 92.68% | 73.08% | 81.72% |

## Final Test Results

After selecting the original MLP using the validation results, I evaluated it on the test set, which was not used during training or model selection.

| Metric | Score |
|---|---|
| Accuracy | 78.36% |
| Precision | 77.50% |
| Recall | 60.78% |
| F1 Score | 68.13% |

The test accuracy was lower than the validation accuracy. This shows why evaluating a model on completely unseen data is important. The validation set gave a more optimistic result, while the test set provided a more realistic measure of how well the model generalizes.

## Confusion Matrix

The final model correctly predicted:

- 74 passengers who did not survive
- 31 passengers who survived

It made:

- 9 false positive predictions
- 20 false negative predictions

The model was better at identifying passengers who did not survive. The larger number of false negatives also explains why the recall for the survivor class was lower.

## What I learned

This project helped me understand the complete workflow involved in building a machine learning model.

Some of the main things I learned were:

- How to handle missing data
- Why preprocessing is important before training a neural network
- How to encode categorical data and scale numerical features
- Why a baseline model is useful
- How to build and train an MLP for binary classification
- How to use validation data for comparing models
- How to analyze training and validation curves
- How Dropout affects neural network training
- Why accuracy alone is not enough to evaluate a model
- Why final evaluation should be done on unseen test data

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow
- Keras
- Matplotlib
- Seaborn
- Google Colab

## Project Files

```text
titanic-survival-prediction-mlp/
├── Titanic_Survival_Prediction.ipynb
├── README.md
├── requirements.txt
└── data/
    └── titanic.csv
