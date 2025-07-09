# Health Insurance Cost Prediction

A machine learning application that predicts health insurance costs based on various demographic and health-related factors. The application uses a Streamlit web interface for user interaction and employs different models for different age groups.

## Features

- **Age-based Model Selection**: Uses different models for young (≤25 years) and older (>25 years) individuals
- **Interactive Web Interface**: Built with Streamlit for easy user interaction
- **Comprehensive Input Fields**: Captures demographic, health, and lifestyle information
- **Real-time Predictions**: Instant insurance cost predictions based on user inputs

## Input Parameters

### Demographic Information
- **Age**: 18-100 years
- **Gender**: Male/Female
- **Marital Status**: Married/Unmarried
- **Number of Dependants**: 0-20
- **Income in Lakhs**: Annual income
- **Employment Status**: Salaried/Self-Employed/Freelancer
- **Region**: Northwest/Southeast/Northeast/Southwest

### Health Information
- **BMI Category**: Normal/Obesity/Overweight/Underweight
- **Smoking Status**: No Smoking/Occasional/Regular
- **Medical History**: Various disease combinations including:
  - No Disease
  - Diabetes
  - High blood pressure
  - Thyroid
  - Heart disease
  - Combinations of the above

### Insurance Details
- **Insurance Plan**: Bronze/Silver/Gold
- **Genetical Risk**: 0-5 scale

## Technical Architecture

### Model Structure
- **Young Model** (`model_young`): For individuals aged ≤25 years
- **Rest Model** (`model_rest`): For individuals aged >25 years
- **Scalers**: Separate scaling for each age group

### Data Preprocessing
- **Feature Engineering**: One-hot encoding for categorical variables
- **Risk Score Calculation**: Normalized risk scores based on medical history
- **Scaling**: Age-appropriate feature scaling

### File Structure
```
Health_premium_Prediction/
├── app/
│   ├── main.py                 # Streamlit web application
│   ├── prediction_helpwer.py   # ML prediction logic
│   └── artifacts/              # Trained models and scalers
│       ├── best_model.joblib
│       ├── model_rest.joblib
│       ├── scaler_young.joblib
│       └── scaler_rest.joblib
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation

1. **Clone the repository**:
   ```bash
   [git clone <repository-url>](https://github.com/shivsharankumar/Health-Premium-Prediction.git)
   cd Health_premium_Prediction
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**:
   ```bash
   streamlit run app/main.py
   ```
4. Hosted at : https://shiv-health-premium-prediction.streamlit.app/
## Usage

1. Open your web browser and navigate to the Streamlit app (usually `http://localhost:8501`)
2. Fill in the required information in the form fields
3. Click the "Predict" button to get your health insurance cost prediction
4. The prediction will be displayed at the bottom of the page

## Model Performance

The application uses separate models for different age groups to improve prediction accuracy:
- **Young Model**: Optimized for individuals aged 18-25
- **Rest Model**: Optimized for individuals aged 26-100

## Risk Score Calculation

The application calculates a normalized risk score based on medical history:
- **Diabetes**: 6 points
- **Heart Disease**: 8 points
- **High Blood Pressure**: 6 points
- **Thyroid**: 5 points
- **No Disease**: 0 points

The final risk score is normalized to a 0-1 scale.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Built as part of the CodeBasics ML course
- Uses Streamlit for the web interface
- Implements machine learning models for insurance cost prediction

## Contact

For questions or support, please open an issue in the repository. 
