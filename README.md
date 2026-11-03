# Healthcare Email Spam Classifier

A machine learning-powered web application that classifies emails as **Spam** or **Not Spam** using Natural Language Processing (NLP) and supervised learning. Built with Flask and Scikit-learn, the application uses a trained Multinomial Naive Bayes model to analyze email content and identify potentially unwanted messages.

## Features

- **Email Classification:** Classifies email messages as Spam or Not Spam.
- **Machine Learning Model:** Uses Multinomial Naive Bayes for binary text classification.
- **Text Feature Extraction:** Converts email text into numerical features using CountVectorizer.
- **Web Interface:** Provides a simple interface for submitting email content and viewing predictions.
- **Model Persistence:** Saves the trained model using Pickle for reuse without retraining.
- **Model Evaluation:** Splits the dataset into training and testing sets to evaluate classification accuracy.

## Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Frontend | HTML, CSS |
| Backend | Flask |
| Machine Learning | Scikit-learn, Multinomial Naive Bayes |
| NLP / Text Processing | CountVectorizer |
| Data Processing | Pandas, NumPy |
| Model Serialization | Pickle |
| Dataset | Mail_Data.csv |

## Project Structure

```text
Medithon_code-X/
│
├── templates/
│   └── index.html                 # Web application interface
│
├── Mail_Data.csv                  # Email classification dataset
├── app.py                         # Flask application
├── train_model.py                 # Model training and evaluation
├── email_classifier_model.pkl     # Trained ML model
└── README.md                      # Project documentation
```

## How It Works

The application follows this workflow:

1. **Dataset Loading:** Loads labeled email messages from `Mail_Data.csv`.
2. **Data Preprocessing:** Converts email categories into binary labels (Spam = 1, Not Spam = 0).
3. **Feature Extraction:** Uses CountVectorizer to transform email text into numerical feature vectors.
4. **Model Training:** Trains a Multinomial Naive Bayes classifier using the extracted features.
5. **Model Evaluation:** Evaluates the trained model using a 75:25 training-testing split.
6. **Model Persistence:** Saves the trained classification pipeline as a Pickle file.
7. **Email Prediction:** Accepts email content through the Flask web interface and predicts whether it is spam or legitimate.

## Machine Learning Model

**Algorithm:** Multinomial Naive Bayes

**Feature Extraction:** CountVectorizer

The model uses word-frequency features to identify patterns associated with spam and legitimate emails.

| Parameter | Configuration |
|---|---|
| Algorithm | Multinomial Naive Bayes |
| Feature Extraction | CountVectorizer |
| Training Data | 75% |
| Testing Data | 25% |
| Random State | 42 |
| Classification Type | Binary Classification |

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/abishekgvincent/Medithon_code-X.git
cd Medithon_code-X
```

### 2. Install Dependencies

```bash
pip install flask pandas numpy scikit-learn
```

### 3. Train the Machine Learning Model (Optional)

To retrain the model using the dataset:

```bash
python train_model.py
```

This generates the trained model file:

```text
email_classifier_model.pkl
```

### 4. Run the Application

```bash
python app.py
```

### 5. Access the Web Application

Open your browser and navigate to:

```text
http://127.0.0.1:5000/
```

Enter an email message and submit it to receive the classification result.

## Model Evaluation

The model evaluates its performance using the test dataset and prints the classification accuracy:

```text
Model Accuracy: <calculated accuracy>%
```

The accuracy is calculated using Scikit-learn's pipeline scoring method.

## Future Enhancements

- Implement advanced text preprocessing and stopword removal.
- Explore TF-IDF for improved text feature representation.
- Evaluate additional algorithms such as Logistic Regression and Support Vector Machines.
- Add precision, recall, F1-score, and confusion matrix evaluation.
- Improve the web interface with email classification history.
- Extend classification to detect phishing and malicious healthcare-related emails.
