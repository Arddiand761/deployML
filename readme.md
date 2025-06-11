# Backend ML - Financial Prediction API

API Flask untuk prediksi keuangan dan deteksi anomali menggunakan Machine Learning.

## 🚀 Features

- **Prediksi Keuangan**: Endpoint untuk prediksi data keuangan
- **Deteksi Anomali**: Sistem deteksi anomali untuk transaksi keuangan
- **API Key Authentication**: Keamanan dengan API Key
- **Health Check**: Status monitoring untuk model ML

## 🛠 Tech Stack

- **Backend**: Flask
- **Machine Learning**: Scikit-learn, TensorFlow
- **Data Processing**: Pandas, NumPy
- **NLP**: NLTK
- **Deployment**: Railway, Gunicorn

## 📋 Requirements

```txt
Flask==3.1.1
gunicorn==23.0.0
python-dotenv==1.1.0
scikit-learn==1.6.1
numpy==1.26.4
pandas==2.3.0
tensorflow==2.16.1
nltk==3.9.1
```

## 🔧 Installation

1. **Clone repository**

```bash
git clone <repository-url>
cd backendML-main
```

2. **Create virtual environment**

```bash
python -m venv .venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Linux/Mac
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Setup environment variables**

```bash
# Create .env file
PYTHON_API_KEY=your_secret_api_key_here
```

5. **Run application**

```bash
python app.py
```

## 🌐 API Endpoints

### Health Check

```http
GET /
```

**Response:**

```json
{
  "message": "Selamat Datang di API Keuangan",
  "status_model_prediksi_anomali": "Model loaded successfully"
}
```

### Financial Prediction

```http
POST /predict/keuangan
Content-Type: application/json
X-API-Key: your_api_key
```

**Request Body:**

```json
{
  "data": "your_financial_data"
}
```

**Response:**

```json
{
  "prediksi_keuangan": "prediction_result"
}
```

### Anomaly Detection

```http
POST /predict/anomaly
Content-Type: application/json
X-API-Key: your_api_key
```

## 🔐 Authentication

API menggunakan API Key authentication melalui header `X-API-Key`.

Set environment variable:

```bash
PYTHON_API_KEY=your_secret_key
```

## 🚢 Deployment

### Railway Deployment

1. **Create required files:**

   - `Procfile`: `web: gunicorn app:app`
   - `requirements.txt`: Dependencies list
   - `railway.json`: Railway configuration (optional)

2. **Push to GitHub**

```bash
git add .
git commit -m "Initial commit"
git push origin main
```

3. **Deploy on Railway:**
   - Connect GitHub repository
   - Set environment variables in Railway dashboard
   - Deploy automatically

### Environment Variables (Railway)

```
PYTHON_API_KEY=your_secret_api_key
PORT=8080
```

## 📁 Project Structure

```
backendML-main/
├── app.py              # Main Flask application
├── Prediksi.py         # Financial prediction module
├── Anomali.py          # Anomaly detection module
├── requirements.txt    # Python dependencies
├── Procfile           # Railway deployment config
├── .env               # Environment variables (local)
├── .gitignore         # Git ignore rules
└── README.md          # Project documentation
```

## 🔍 Error Handling

API mengembalikan error responses dengan format:

```json
{
  "error": "Error message description"
}
```

**Common HTTP Status Codes:**

- `200`: Success
- `400`: Bad Request (Invalid JSON)
- `401`: Unauthorized (Invalid API Key)
- `500`: Internal Server Error

## 🧪 Testing

Test API endpoints menggunakan tools seperti:

- **Postman**
- **curl**
- **Thunder Client** (VS Code extension)

Example curl request:

```bash
curl -X POST https://your-railway-app.railway.app/predict/keuangan \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your_api_key" \
  -d '{"data": "test_data"}'
```

## 📝 Notes

- Model ML di-pickle dengan scikit-learn versi 1.6.1
- Pastikan konsistensi versi dependencies
- API Key wajib untuk semua endpoints kecuali health check
- Support deployment di Railway dengan Pro plan untuk TensorFlow

## 🤝 Contributing

1. Fork repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create Pull Request

## 📄 License

This project is licensed under the MIT License.
