# Credit Card Fraud Detection using KNN

This project implements a K-Nearest Neighbors (KNN) machine learning model to detect fraudulent credit card transactions. It includes a Flask backend for predictions and a web-based frontend for user interaction. The model is trained on the [Credit Card Fraud Detection dataset from Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).

## Project Structure
```
credit_card_fraud_detection/
├── data/
│   └── creditcard.csv  # Dataset (download from Kaggle)
├── static/
│   ├── css/
│   │   └── style.css   # Frontend styling
│   └── js/
│       └── script.js   # Frontend logic
├── templates/
│   └── index.html      # Frontend HTML
├── app.py              # Flask backend
├── model.py            # KNN model training
├── requirements.txt    # Python dependencies
├── notebook/
│   └── knn_fraud_detection.ipynb  # Colab notebook
└── README.md           # This file
```

## Dataset
- **Source**: Kaggle Credit Card Fraud Detection
- **Features**: 30 numerical features (V1-V28 from PCA, Time, Amount)
- **Target**: Binary (0 = Non-Fraud, 1 = Fraud)
- **Size**: 284,807 transactions, highly imbalanced (0.17% fraud)

## Setup Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/credit_card_fraud_detection.git
   cd credit_card_fraud_detection
   ```

2. **Download Dataset**:
   - Download `creditcard.csv` from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).
   - Place it in the `data/` folder.

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Train Model in Google Colab**:
   - Open `notebook/knn_fraud_detection.ipynb` in Google Colab.
   - Upload `creditcard.csv` or mount Google Drive.
   - Run all cells to train the KNN model and download `knn_model.pkl` and `scaler.pkl`.
   - Place these files in the project root.

5. **Run the Flask App**:
   ```bash
   python app.py
   ```
   - Open `http://localhost:5000` in your browser.

## Usage
- Access the web interface at `http://localhost:5000`.
- Enter values for the 30 transaction features (V1-V28, Time, Amount).
- Click "Predict" to see if the transaction is fraudulent or non-fraudulent, along with the confidence score.

## Model Details
- **Algorithm**: K-Nearest Neighbors (k=5)
- **Preprocessing**: StandardScaler for feature scaling, SMOTE for handling class imbalance
- **Evaluation**: Confusion matrix, precision, recall, F1-score
- **Saved Artifacts**: `knn_model.pkl` (model), `scaler.pkl` (scaler)

## Deployment
- **Local**: Run `app.py` for local testing.
- **Cloud**: Deploy to Heroku, Render, or a VPS. Update `app.py` to use `app.run(host='0.0.0.0', port=8080)` for cloud hosting.
- **Dataset Note**: Due to size, `creditcard.csv` is not included. Download from Kaggle.

## Contributing
Feel free to fork, create issues, or submit pull requests. Ensure code follows PEP 8 and includes tests.

## License
MIT [LICENSE](LICENSE)
