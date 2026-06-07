# Insurance Charges Prediction Model - Streamlit Deployment

A web application to predict health insurance charges based on patient information using Ridge Regression.

## 📋 Features

- 🏥 Predict annual insurance charges
- 📊 Risk assessment (Low/Medium/High)
- 📝 Interactive input form
- 💰 Monthly cost breakdown
- ✅ Model validation with R² scoring

## 🚀 Quick Start

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Ensure Data File

Make sure `insurance.csv` is in the same directory as `app.py`:
```
ch_1/
├── app.py
├── insurance.csv
├── requirements.txt
└── README.md
```

### 3. Run the Streamlit App

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`

## 📱 How to Use

1. **Adjust Sliders**: Use the left sidebar to input patient information
   - Age (18-100)
   - BMI (10-50)
   - Number of Children (0-5)

2. **Select Dropdowns**:
   - Gender: Male/Female
   - Smoker Status: Yes/No
   - Region: Northeast/Northwest/Southeast/Southwest

3. **View Prediction**: The annual insurance charge prediction appears instantly

4. **Risk Assessment**: Get a risk level indicator (Low/Medium/High)

## 🤖 Model Details

- **Algorithm**: Ridge Regression with Cross-Validation
- **Features Used**:
  - Age (scaled)
  - Gender (binary)
  - BMI (scaled)
  - Number of Children (scaled)
  - Smoker Status (binary)
  - Region (one-hot encoded)
  - BMI Category (one-hot encoded)

- **Training Data**: 80% train / 20% test split
- **Cross-Validation**: 5-fold with alpha tuning

## 📊 Model Performance

The model uses GridSearchCV to find optimal hyperparameters and achieves high accuracy on the test set.

## 🔧 Troubleshooting

### Error: "insurance.csv not found"
- Ensure the CSV file is in the same directory as `app.py`

### Error: "Module not found"
- Run: `pip install -r requirements.txt`

### App not opening in browser
- Check the terminal output for the URL (usually `http://localhost:8501`)

## 🌐 Deployment Options

### Local Machine
```bash
streamlit run app.py
```

### Streamlit Cloud (Free)
1. Push your files to GitHub
2. Go to [share.streamlit.io](https://share.streamlit.io)
3. Connect your GitHub repo and deploy

### Cloud Platforms
- **Heroku**: Create a `Procfile` and `setup.sh`
- **AWS**: Use EC2 or AWS Lambda
- **Azure**: Use Azure App Service

## 📝 Example Heroku Deployment

Create `Procfile`:
```
web: streamlit run --logger.level=error app.py
```

Create `setup.sh`:
```bash
mkdir -p ~/.streamlit/
echo "[server]
headless = true
port = $PORT
enableCORS = false
" > ~/.streamlit/config.toml
```

Deploy:
```bash
heroku create your-app-name
git push heroku main
```

## 📚 Required Files

- `app.py` - Main Streamlit application
- `insurance.csv` - Insurance dataset
- `requirements.txt` - Python dependencies
- `README.md` - Documentation (this file)

## 📄 License

Open source for educational purposes

## 👨‍💻 Author

Machine Learning Project - Chapter 1
