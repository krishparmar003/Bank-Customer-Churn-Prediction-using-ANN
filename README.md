# 🏦 Bank Customer Churn Prediction using ANN

An end-to-end deep learning project that predicts whether a bank customer is likely to **leave (churn)** or **stay**, using an **Artificial Neural Network (ANN)** built with TensorFlow/Keras and served through an interactive **Streamlit** app.

The repo also includes a second model, an **ANN regression model** for estimating customer salary, along with hyperparameter tuning and TensorBoard experiments.

🔗 **Live Demo:** [YOUR_STREAMLIT_APP_LINK](YOUR_STREAMLIT_APP_LINK)

---

## 📌 Overview

Losing customers is expensive for any bank, and it is usually cheaper to keep an existing customer than to find a new one. This project uses customer details like geography, gender, age, balance and activity to predict the chance that a customer will churn, so the bank can act before they leave.

What this project covers:

1. **Data preprocessing:** encoding categorical features (Gender, Geography) and scaling numeric features
2. **ANN model building and training** for churn classification
3. **Experiment tracking** with TensorBoard
4. **Hyperparameter tuning** of the ANN
5. **Salary regression** with a separate ANN model
6. **Deployment** as a Streamlit web app

---

## 📂 Project Structure

```
Bank-Customer-Churn-Prediction-using-ANN/
│
├── app.py                      # Streamlit web app
├── Churn_Modelling.csv         # Dataset
│
├── experiments.ipynb           # Data preprocessing, ANN training, TensorBoard logging
├── hptuning_ann.ipynb          # Hyperparameter tuning for the ANN
├── prediction.ipynb            # Loading the saved model and predicting for a new customer
├── salaryregression.ipynb      # ANN regression model for salary prediction
│
├── model.h5                    # Trained churn classification model
├── regression_model.h5         # Trained salary regression model
├── label_encoder_gender.pkl    # Saved label encoder (Gender)
├── onehot_encoder_geo.pkl      # Saved one-hot encoder (Geography)
├── scaler.pkl                  # Saved feature scaler
│
├── logs/fit/                   # TensorBoard logs (classification)
├── regressionlogs/fit/         # TensorBoard logs (regression)
│
├── requirements.txt            # Python dependencies
├── .gitignore
└── README.md
```

---

## 🛠️ Tech Stack

- **Python 3.10**
- **TensorFlow / Keras:** ANN model building and inference
- **scikit-learn:** encoding, scaling and preprocessing
- **Pandas, NumPy:** data handling
- **TensorBoard:** training visualization
- **Streamlit:** web app and deployment

---

## 🚀 Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/krishparmar003/Bank-Customer-Churn-Prediction-using-ANN.git
cd Bank-Customer-Churn-Prediction-using-ANN
```

### 2. Create a virtual environment

**Windows**
```bash
py -3.10 -m venv myenv
```

**macOS / Linux**
```bash
python3.10 -m venv myenv
```

### 3. Activate the virtual environment

**Windows (Command Prompt)**
```bash
myenv\Scripts\activate.bat
```

**Windows (PowerShell)**
```powershell
myenv\Scripts\activate
```

**macOS / Linux**
```bash
source myenv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Streamlit app

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

---

## 💡 How to Use

1. Open the app (live link above, or locally).
2. Enter the customer's details such as geography, gender, age, balance, credit score, tenure, number of products and activity status.
3. The app preprocesses the input using the saved encoders and scaler, then runs it through the trained model.
4. You get the **churn probability** and whether the customer is likely to leave or stay.

---

## 📓 Notebooks

To explore the full workflow, run the notebooks with Jupyter:

```bash
jupyter notebook
```

| Notebook | What it covers |
|----------|----------------|
| `experiments.ipynb` | Preprocessing, building and training the ANN, TensorBoard logging |
| `hptuning_ann.ipynb` | Hyperparameter tuning to find a better ANN configuration |
| `prediction.ipynb` | Loading the saved model, encoders and scaler to predict on new data |
| `salaryregression.ipynb` | Building an ANN regression model to predict salary |

---

## 📊 View Training Logs with TensorBoard

```bash
tensorboard --logdir logs/fit
```

For the regression model:

```bash
tensorboard --logdir regressionlogs/fit
```

Then open `http://localhost:6006` in your browser.

---

## ⚠️ Important Notes

- `model.h5`, `regression_model.h5` and the `.pkl` files must stay in the project root. The app loads them from there.
- Use the same library versions as in `requirements.txt`. The saved encoders and scaler may not load correctly with very different scikit-learn versions.


