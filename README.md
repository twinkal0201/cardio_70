# CardioAI Dashboard - Quick Start Guide

## 🚀 Getting Started

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Start the Backend Server
```bash
python predict.py
```
The server will start on `http://localhost:5000`

### 3. Open the Dashboard
Open `index.html` in your web browser (Chrome, Firefox, or Edge recommended)

---

## 📁 Project Structure

```
projectUi/
├── index.html          # Main dashboard HTML
├── style.css           # Glassmorphism theme & animations
├── app.js              # Frontend logic & charts
├── predict.py          # Flask backend API
├── requirements.txt    # Python dependencies
└── models/
    ├── random_forest_model.pkl
    └── scaler.pkl
```

---

## 🎨 Features

### ✅ Dashboard Sections
- **Dashboard**: Overview with statistics and charts
- **Patient Input**: Multi-step form with 11 medical parameters
- **Prediction Result**: Animated risk indicator with AI explanation
- **Model Performance**: Accuracy, precision, recall, F1-score, ROC curve
- **Risk Analytics**: Interactive charts and visualizations
- **History**: Track past predictions (stored locally)
- **About Model**: Information about the AI model

### ✅ UI/UX Features
- Glassmorphism design with backdrop blur
- Dark/Light mode toggle
- Heart-beat loading animations
- Micro-interactions on hover
- Responsive design (mobile-friendly)
- Toast notifications
- Form validation with progress tracking

### ✅ Charts & Analytics
- Risk distribution (doughnut chart)
- Recent predictions timeline
- Feature importance (horizontal bar)
- ROC curve
- Confusion matrix
- Heart rate vs age scatter plot
- Cholesterol distribution
- Risk by age group (stacked bar)

---

## 🔧 API Endpoints

### POST `/predict`
Predict cardiovascular disease risk

**Request Body:**
```json
{
  "age": 55,
  "sex": 1,
  "cp": 0,
  "trestbps": 130,
  "chol": 250,
  "fbs": 0,
  "restecg": 0,
  "thalach": 150,
  "exang": 0,
  "oldpeak": 1.5,
  "slope": 1
}
```

**Response:**
```json
{
  "prediction": 1,
  "risk_level": "moderate",
  "risk_score": 65.5,
  "confidence": 92.3,
  "explanation": "Based on patient data...",
  "status": "success"
}
```

### GET `/health`
Health check endpoint

---

## 🎯 Usage Tips

1. **Dark/Light Mode**: Click the sun/moon icon in the header
2. **Navigation**: Use the sidebar to switch between sections
3. **Patient Input**: Fill all 11 fields and click "Predict Risk"
4. **Save History**: After prediction, click "Save to History"
5. **View Charts**: Navigate to different sections to see analytics

---

## 🔒 Medical Disclaimer

This tool is for educational and research purposes only. It should not replace professional medical advice, diagnosis, or treatment. Always consult with a qualified healthcare provider.

---

## 🛠️ Troubleshooting

**Backend not connecting?**
- Ensure Flask server is running on port 5000
- Check console for CORS errors
- The frontend will use demo predictions if backend is unavailable

**Charts not displaying?**
- Ensure Chart.js CDN is loaded
- Check browser console for errors
- Try refreshing the page

**Styling issues?**
- Clear browser cache
- Ensure `style.css` is in the same directory
- Check if browser supports `backdrop-filter` (for glassmorphism)

---

## 📊 Model Information

- **Algorithm**: Random Forest Classifier
- **Accuracy**: 94.2%
- **Features**: 11 clinical parameters
- **Training Samples**: 918 patient records

---

Enjoy using CardioAI! 🫀
