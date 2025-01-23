# Market Crash Prediction System

This project provides a comprehensive framework for predicting potential market crashes using financial market data. The system includes a trained Random Forest model, preprocessing pipelines, and a web interface to interact with the predictions and recommendations. It also generates investment strategies using an advanced language model.

## Features

1. **Crash Probability Prediction**: Uses financial market indicators to predict the probability of a market crash.
2. **Investment Strategy Recommendations**: Suggests detailed investment strategies based on the prediction.
3. **Web Interface**: Includes a Streamlit app for user-friendly interaction and a Flask-based REST API for programmatic access.
4. **Data Visualization and Analysis**: Provides insights and analysis of market trends.

## File Structure

- `app.py`: A Streamlit application for interactive prediction and strategy recommendations.
- `main.py`: A Flask API for programmatic access to the prediction model.
- `Market crash.ipynb`: A Jupyter Notebook containing exploratory data analysis (EDA), model training, and evaluation.
- `rf_model.pkl`: Trained Random Forest model.
- `scaler.pkl`: Scaler for feature normalization.
- `imputer.pkl`: Imputer for handling missing values.
- `data_1.xlsx`: Dataset containing historical financial data.

## Requirements

- Python 3.8+
- Required libraries: See `requirements.txt`

## Installation

1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Place the model files:**
   Ensure `rf_model.pkl`, `scaler.pkl`, and `imputer.pkl` are in the root directory.

5. **Add the dataset:**
   Place `data_1.xlsx` in the root directory.

## Usage

### Streamlit App

1. **Run the Streamlit application:**
   ```bash
   streamlit run app.py
   ```

2. **Interact with the app:**
   - Select a date from the sidebar dropdown to load example data.
   - Modify features using the input fields.
   - Click "Predict" to view crash probability and receive investment strategy recommendations.

### Flask API

1. **Run the Flask API:**
   ```bash
   python main.py
   ```

2. **Send a POST request to `/predict` endpoint:**
   ```bash
   curl -X POST http://127.0.0.1:5000/predict -H "Content-Type: application/json" -d '{"XAU BGNL": 1500, "ECSURPUS": 300, ...}'
   ```
   Replace `...` with the actual feature values.

3. **Receive the response:**
   ```json
   {
       "crash_probability": 0.85,
       "prediction": 1
   }
   ```

### Jupyter Notebook

1. Open `Market crash.ipynb` in Jupyter Notebook.
2. Execute cells to view the data exploration, preprocessing, model training, and evaluation steps.

## Model Details

- **Algorithm**: Random Forest Classifier
- **Input Features**: A set of 43 financial indicators (e.g., gold price, bond yields, cryptocurrency indices).
- **Output**: Probability of a market crash and binary classification (1 = Crash, 0 = No Crash).

## Preprocessing

1. **Missing Values**: Handled using `imputer.pkl`.
2. **Feature Scaling**: Applied using `scaler.pkl`.

## Advanced Features

- **Investment Strategy Recommendations**: Generates strategies for market conditions using a language model integrated with OpenAI’s API.
- **Real-time Interaction**: Predict market conditions based on current data.

