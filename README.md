<div align="center">

# 🌱 AGRISMART

### Crop Yield Prediction & Recommendation System

<p>
  <b>Machine Learning-Based Agricultural Decision Support System</b>
</p>

<p>
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Random%20Forest-Regression-2E8B57?style=for-the-badge">
  <img src="https://img.shields.io/badge/Logistic%20Regression-Classification-6A5ACD?style=for-the-badge">
</p>

<p>
  <i>
    An end-to-end Machine Learning project that predicts crop yield
    and recommends suitable crops based on soil and environmental conditions.
  </i>
</p>

</div>

<hr>

## 📌 Overview

<b>AGRISMART</b> is a Machine Learning-based agricultural decision support system designed to help identify suitable crops and estimate expected crop yield using environmental and soil-related parameters.

The project combines two Machine Learning tasks:

<ul>
  <li>
    <b>🌾 Crop Yield Prediction</b> – Predicts crop yield using a Random Forest Regression model.
  </li>
  <li>
    <b>🌱 Crop Recommendation</b> – Recommends suitable crops using a Logistic Regression classification model.
  </li>
</ul>

The recommendation system goes beyond simply predicting a single crop by generating the <b>Top 3 suitable crops</b> along with their corresponding probability scores.

---

## 🎯 Project Objectives

<ul>
  <li>Predict expected crop yield using historical agricultural data.</li>
  <li>Identify the most suitable crop based on soil and environmental conditions.</li>
  <li>Provide probability scores for recommended crops.</li>
  <li>Generate the Top 3 crop recommendations.</li>
  <li>Apply appropriate data preprocessing and Machine Learning techniques.</li>
  <li>Evaluate model performance using relevant regression and classification metrics.</li>
</ul>

---

## 🧠 Machine Learning Approach

<table>
<tr>
<th>Task</th>
<th>Problem Type</th>
<th>Algorithm</th>
<th>Evaluation</th>
</tr>

<tr>
<td>🌾 Crop Yield Prediction</td>
<td>Regression</td>
<td><b>Random Forest Regressor</b></td>
<td>R² Score</td>
</tr>

<tr>
<td>🌱 Crop Recommendation</td>
<td>Classification</td>
<td><b>Logistic Regression</b></td>
<td>Accuracy, Precision, Recall, F1-Score</td>
</tr>
</table>

---

## 📊 Model Performance

### 🌾 Crop Yield Prediction

A <b>Random Forest Regression</b> model was developed to predict crop yield based on agricultural and environmental features.

<table>
<tr>
<th>Metric</th>
<th>Score</th>
</tr>

<tr>
<td><b>Test R² Score</b></td>
<td><b>98.83%</b></td>
</tr>

<tr>
<td><b>Mean 5-Fold Cross-Validation R²</b></td>
<td><b>96.52%</b></td>
</tr>
</table>

<p>
The high R² score indicates that the model explains a large proportion of the variation in crop yield within the evaluated dataset.
</p>

---

### 🌱 Crop Recommendation

A <b>Logistic Regression</b> classification model was developed to recommend suitable crops based on soil and environmental conditions.

<table>
<tr>
<th>Metric</th>
<th>Score</th>
</tr>

<tr>
<td><b>Accuracy</b></td>
<td><b>97.50%</b></td>
</tr>

<tr>
<td><b>Precision</b></td>
<td><b>97.62%</b></td>
</tr>

<tr>
<td><b>Recall</b></td>
<td><b>97.50%</b></td>
</tr>

<tr>
<td><b>F1-Score</b></td>
<td><b>97.50%</b></td>
</tr>
</table>

---

## 🌾 Top 3 Crop Recommendation

One of the key features of AGRISMART is its ability to provide multiple crop recommendations rather than returning only one prediction.

The classification model generates probability scores using:

```python
model.predict_proba()
```

The probabilities are then sorted to identify the three crops with the highest predicted suitability.

### Example

```text
Input Conditions
│
├── Nitrogen
├── Phosphorus
├── Potassium
├── Temperature
├── Humidity
├── pH
└── Rainfall
        │
        ▼
  Logistic Regression
        │
        ▼
 Probability Scores
        │
        ▼
 ┌─────────────────────────────┐
 │ Top 3 Crop Recommendations  │
 ├─────────────────────────────┤
 │ 1. Crop A → 94.2%           │
 │ 2. Crop B → 87.6%           │
 │ 3. Crop C → 81.4%           │
 └─────────────────────────────┘
```

<i>The crop names and probability values above are illustrative examples.</i>

---

## 🔄 Project Workflow

<div align="center">

```text
             ┌──────────────────────┐
             │   Agricultural Data  │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │   Data Preprocessing │
             │ Cleaning & Validation│
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │ Exploratory Analysis │
             │ & Feature Analysis   │
             └──────────┬───────────┘
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
   ┌──────────────────┐  ┌──────────────────┐
   │ Yield Prediction │  │ Crop Recommend.  │
   │    Regression    │  │ Classification   │
   └────────┬─────────┘  └────────┬─────────┘
            │                     │
            ▼                     ▼
   ┌──────────────────┐  ┌──────────────────┐
   │ Random Forest    │  │ Logistic         │
   │ Regressor        │  │ Regression       │
   └────────┬─────────┘  └────────┬─────────┘
            │                     │
            ▼                     ▼
   ┌──────────────────┐  ┌──────────────────┐
   │ Yield Prediction │  │ Top 3 Crops +    │
   │                  │  │ Probability      │
   └──────────────────┘  └──────────────────┘
```

</div>

---

## 🔬 Data Processing

The project follows a structured Machine Learning workflow:

<ol>
  <li><b>Data Collection</b> – Agricultural and environmental data is collected for model development.</li>
  <li><b>Data Cleaning</b> – Missing values, duplicate records and inconsistent data are handled.</li>
  <li><b>Exploratory Data Analysis</b> – Data distributions and relationships between features are analyzed.</li>
  <li><b>Feature Preparation</b> – Relevant features are selected and prepared for modeling.</li>
  <li><b>Train-Test Split</b> – Data is divided into training and testing subsets.</li>
  <li><b>Model Training</b> – Regression and classification models are trained.</li>
  <li><b>Model Evaluation</b> – Models are evaluated using appropriate performance metrics.</li>
  <li><b>Prediction</b> – The trained models generate yield predictions and crop recommendations.</li>
</ol>

---

## 🛠️ Technologies & Libraries

<table>
<tr>
<td><b>Programming Language</b></td>
<td>Python</td>
</tr>

<tr>
<td><b>Data Manipulation</b></td>
<td>Pandas, NumPy</td>
</tr>

<tr>
<td><b>Machine Learning</b></td>
<td>Scikit-learn</td>
</tr>

<tr>
<td><b>Regression</b></td>
<td>Random Forest Regressor</td>
</tr>

<tr>
<td><b>Classification</b></td>
<td>Logistic Regression</td>
</tr>

<tr>
<td><b>Visualization</b></td>
<td>Matplotlib, Seaborn</td>
</tr>

<tr>
<td><b>Development Environment</b></td>
<td>Jupyter Notebook / Google Colab / VS Code</td>
</tr>
</table>

---

## 📂 Project Structure

```text
AGRISMART/
│
├── 📁 dataset/
│   ├── crop_yield.csv
│   └── crop_recommendation.csv
│
├── 📁 notebooks/
│   ├── crop_yield_prediction.ipynb
│   └── crop_recommendation.ipynb
│
├── 📁 models/
│   ├── yield_model.pkl
│   └── crop_recommendation_model.pkl
│
├── 📁 src/
│   ├── preprocessing.py
│   ├── yield_prediction.py
│   └── crop_recommendation.py
│
├── 📁 images/
│   ├── eda.png
│   ├── model_performance.png
│   └── recommendation_output.png
│
├── requirements.txt
├── README.md
└── LICENSE
```

<i>Update the folder structure above according to the actual files in your repository.</i>

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/AGRISMART.git
cd AGRISMART
```

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

### 3️⃣ Activate the Environment

<b>Windows:</b>

```bash
venv\Scripts\activate
```

<b>macOS / Linux:</b>

```bash
source venv/bin/activate
```

### 4️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ How to Run

If the project is implemented using Jupyter Notebook:

```bash
jupyter notebook
```

Then open the relevant notebook:

```text
notebooks/
├── crop_yield_prediction.ipynb
└── crop_recommendation.ipynb
```

Run the notebook cells sequentially to perform:

```text
Data Loading
     ↓
Data Preprocessing
     ↓
EDA
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Prediction
     ↓
Crop Recommendation
```

---

## 📈 Evaluation Metrics

### Regression

<b>R² Score</b> was used to evaluate the crop-yield prediction model.

The model achieved:

```text
Test R² Score                  : 98.83%
Mean 5-Fold CV R² Score        : 96.52%
```

### Classification

The crop recommendation model was evaluated using:

```text
Accuracy  : 97.50%
Precision : 97.62%
Recall    : 97.50%
F1-Score  : 97.50%
```

These metrics provide a broader evaluation of classification performance rather than relying only on accuracy.

---

## 💡 Key Features

<table>
<tr>
<td>🌾</td>
<td><b>Crop Yield Prediction</b></td>
<td>Predicts expected crop yield using Random Forest Regression.</td>
</tr>

<tr>
<td>🌱</td>
<td><b>Crop Recommendation</b></td>
<td>Identifies suitable crops using Logistic Regression.</td>
</tr>

<tr>
<td>🎯</td>
<td><b>Top-3 Recommendations</b></td>
<td>Provides the three most suitable crops based on predicted probabilities.</td>
</tr>

<tr>
<td>📊</td>
<td><b>Model Evaluation</b></td>
<td>Uses regression and classification metrics to assess model performance.</td>
</tr>

<tr>
<td>🔬</td>
<td><b>Data Analysis</b></td>
<td>Includes preprocessing and exploratory analysis of agricultural data.</td>
</tr>
</table>

---

## 🚀 Future Improvements

<ul>
  <li>Develop a web-based interface for farmers and agricultural users.</li>
  <li>Integrate real-time weather and environmental data.</li>
  <li>Add more regional soil and crop datasets.</li>
  <li>Experiment with advanced ensemble and boosting algorithms.</li>
  <li>Deploy the trained models using Flask, FastAPI, or Streamlit.</li>
  <li>Add explainable AI techniques to show why a crop was recommended.</li>
  <li>Integrate location-specific recommendations based on geographical conditions.</li>
</ul>

---

## 📌 Key Learning Outcomes

Through this project, the following Machine Learning concepts were implemented:

<ul>
  <li>Data preprocessing and feature preparation</li>
  <li>Exploratory Data Analysis</li>
  <li>Regression modeling</li>
  <li>Classification modeling</li>
  <li>Random Forest</li>
  <li>Logistic Regression</li>
  <li>Cross-validation</li>
  <li>Model evaluation</li>
  <li>Probability-based predictions</li>
  <li>Top-K recommendation logic</li>
</ul>

---

## 👩‍💻 Author

<div align="center">

### Komal Verma

<b>Data Science | Machine Learning | Python</b>

<p>
  <i>Interested in building practical Machine Learning solutions for real-world problems.</i>
</p>

</div>

---

## ⭐ Project Highlights

```text
🌱 AGRISMART
│
├── 🌾 Crop Yield Prediction
│   └── Random Forest Regression
│       └── Test R²: 98.83%
│
├── 🌱 Crop Recommendation
│   └── Logistic Regression
│       └── Accuracy: 97.50%
│
├── 🎯 Top-3 Crop Recommendations
│   └── Probability-based ranking
│
└── 🧠 End-to-End Machine Learning Workflow
```

<div align="center">

<b>⭐ If you found this project useful, consider giving the repository a star!</b>

<br><br>

<i>Built with Python & Machine Learning 🌱</i>

</div>
