# Titanic Survival Prediction using Neural Networks

This project predicts whether a passenger survived the Titanic disaster using machine learning and a Feed Forward Neural Network.

The project covers data preprocessing, model training, comparison with a baseline model, and final evaluation on unseen test data.

## What I did

- Explored the dataset and checked for missing values
- Filled missing `Age` values using the median
- Filled missing `Embarked` values using the mode
- Removed `Cabin` due to the large number of missing values
- Encoded categorical features
- Scaled numerical features
- Split the data into training, validation, and test sets
- Built Logistic Regression as a baseline
- Built and trained a Multi-Layer Perceptron
- Tested Dropout to check for improvement in generalization
- Evaluated the final model using accuracy, precision, recall, F1 score, and a confusion matrix

## Models and Results

### Logistic Regression

| Metric | Score |
|---|---:|
| Accuracy | 85.82% |
| Precision | 85.11% |
| Recall | 76.92% |
| F1 Score | 80.81% |

### Multi-Layer Perceptron

The neural network uses two hidden layers with 32 and 16 neurons, followed by a sigmoid output layer for binary classification.

| Metric | Score |
|---|---:|
| Accuracy | 87.31% |
| Precision | 92.68% |
| Recall | 73.08% |
| F1 Score | 81.72% |

### MLP with Dropout

I also tested the model with Dropout layers. It produced the same validation performance as the original MLP, so the simpler model was selected as the final model.

| Metric | Score |
|---|---:|
| Accuracy | 87.31% |
| Precision | 92.68% |
| Recall | 73.08% |
| F1 Score | 81.72% |

## Model Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 85.82% | 85.11% | 76.92% | 80.81% |
| Original MLP | 87.31% | 92.68% | 73.08% | 81.72% |
| MLP with Dropout | 87.31% | 92.68% | 73.08% | 81.72% |

## Final Test Results

The final MLP was evaluated on 134 unseen test samples.

| Metric | Score |
|---|---:|
| Accuracy | 78.36% |
| Precision | 77.50% |
| Recall | 60.78% |
| F1 Score | 68.13% |

The final test results were lower than the validation results, showing the importance of evaluating a model on completely unseen data.

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

## Repository Files

```text
titanic-survival-prediction-mlp/
├── README.md
├── Team_Lambda_Titanic_Classification_Revathi.ipynb
└── Titanic-Dataset.csv
```

## What I Learned

This project helped me understand the complete workflow of a binary classification problem, including data preprocessing, baseline comparison, neural network training, regularization, and model evaluation.

It also showed me why a good validation score alone is not enough and why the final test set should remain unseen until the final evaluation.

## Author

**Revathi Krishna P K**  
M.Sc. Artificial Intelligence and Machine Learning
