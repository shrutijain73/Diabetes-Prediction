# 🩺 Diabetes Prediction System

A machine learning-based risk assessment tool that predicts whether a patient is likely to have diabetes based on common medical measurements. It uses a Support Vector Machine (SVM) model, chosen after comparing it with Random Forest, and is deployed as an interactive web app with Streamlit.

**Live demo:** Add your Streamlit app link here

> ⚠️ **Disclaimer:** This project is for educational purposes only. It is not a medical device and is not a substitute for professional medical advice, diagnosis, or treatment.

---

## Features

- Interactive sidebar for entering patient information (age, pregnancies, glucose, blood pressure, skin thickness, insulin, BMI, and more)
- Instant diabetes risk prediction from a trained SVM model
- Input scaling handled automatically with the same scaler used during training
- Clean, simple interface built with Streamlit

## Dataset

The model is trained on the **Pima Indians Diabetes Dataset** (`diabetes.csv`), which contains 768 records and 8 input features:

| Feature | Description |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration (mg/dL) |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skin fold thickness (mm) |
| Insulin | 2-hour serum insulin (mu U/ml) |
| BMI | Body mass index |
| DiabetesPedigreeFunction | Diabetes pedigree function (family history score) |
| Age | Age in years |

The target column, `Outcome`, is `1` for diabetic and `0` for non-diabetic.

## Model Selection

Two models were trained and compared on the same train/test split:

| Model | Test Accuracy |

| Support Vector Machine (SVM) | ~80% |
| Random Forest | ~78% |

**SVM performed better, so it was selected for the final app.**

- **Preprocessing:** Feature scaling with `StandardScaler`
- **Final model:** SVM, saved as `diabetes_model.pkl`
- **Scaler:** saved as `scaler_svm.pkl`

The full training process, including data exploration, preprocessing, model comparison, and evaluation, is in `diabetes-prediction.ipynb`.

## Tech Stack

- Python
- Pandas and NumPy for data handling
- scikit-learn for modeling
- Matplotlib & Seaborn - Data visualization
- Joblib for saving and loading the model
- Streamlit for the web interface

## Project Structure

```
Diabetes Prediction/
├── app.py                      # Streamlit web app
├── diabetes-prediction.ipynb   # Model training and evaluation notebook
├── diabetes.csv                # Dataset
├── diabetes_model.pkl          # Trained SVM model
├── scaler_svm.pkl              # Fitted StandardScaler
├── requirements.txt            # Python dependencies
└── README.md
```
## Project Results
• 80% Test Accuracy
• 76% Precision
• 63% Recall
• Trained on 768 patient records
• 8 medical features analyzed


## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/diabetes-prediction.git
cd diabetes-prediction
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the app

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

### Retraining the model (optional)

Open `diabetes-prediction.ipynb` in Jupyter and run all cells. The notebook will regenerate `diabetes_model.pkl` and `scaler_svm.pkl`.

## How to Use

1. Enter the patient's details in the sidebar.
2. Click **Predict**.
3. View the predicted risk result on the main page.

## Limitations

- The dataset is small (768 records) and comes from a specific population, so results may not generalize to everyone.
- Some measurements in the dataset contain zeros that represent missing values, which can affect accuracy.
- The model gives a statistical estimate, not a diagnosis.

## Future Improvements

- Compare additional models (Random Forest, Logistic Regression, XGBoost)
- Show prediction probability as a gauge or chart
- Add feature importance or an explanation of the result
- Improve handling of missing or zero values

## Author
**Shruti Jain**
