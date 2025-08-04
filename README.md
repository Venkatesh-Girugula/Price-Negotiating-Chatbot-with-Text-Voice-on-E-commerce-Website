# Price-Negotiating-Chatbot-with-Text-Voice-on-E-commerce-Website


## 📦 Price Negotiating Chatbot for E-commerce (with Voice & Text)

This project implements a **Price Negotiation Chatbot** integrated into an e-commerce platform, allowing users to negotiate product prices using **text or voice** commands. The chatbot uses **machine learning (SVR & KNN)** to predict optimal pricing and understands customer sentiment using **VADER Sentiment Analysis**.

---

### 🧠 Features

* Browse e-commerce products with images and prices.
* Negotiate product prices using:

  * **Text-based chatbot**
  * **Voice-based chatbot**
* Dynamic price negotiation using ML models.
* Sentiment-based review analysis.
* Order history and review tracking.

---

### 🛠️ Tech Stack

| Layer              | Technology                               |
| ------------------ | ---------------------------------------- |
| Backend            | Flask (Python Web Framework)             |
| Frontend           | HTML, CSS (rendered via Flask templates) |
| Database           | MySQL (SQL schema provided)              |
| ML Models          | SVR & KNN from scikit-learn              |
| Sentiment Analysis | VADER SentimentIntensityAnalyzer         |
| Voice Processing   | SpeechRecognition + FFMPEG               |

---

### 📁 Project Structure

```bash
├── Main.py                  # Main Flask application
├── test.py                  # Model testing and debugging
├── run.bat                  # Script to launch the webserver
├── requirements.txt         # Python dependencies
├── DB.txt                   # SQL script to create and seed DB
├── SCREENS.docx             # UI flow and screenshots
├── Dataset/
│   ├── model.csv            # Product pricing model (required)
│   └── ecommerce.csv        # Product listings (required)
└── static/
    ├── audio/               # Voice data
    └── img/                 # Product images
```

---

### 🧱 Database Schema

Create the database by executing the commands in `DB.txt`. Here's a quick overview:

* **users**: user credentials and profile
* **purchaseorder**: product orders with timestamp
* **reviews**: user reviews with sentiment

Run via MySQL:

```sql
source DB.txt;
```

---

### 🧰 Installation & Setup

> ⚠️ Prerequisites: Python 3.7+, MySQL Server (username: `root`, password: `root`), pip, ffmpeg

#### 1. Clone the repository

```bash
git clone https://github.com/your-username/price-negotiation-chatbot.git
cd price-negotiation-chatbot
```

#### 2. Install dependencies

```bash
pip install -r requirements.txt
```

#### 3. Setup MySQL database

```bash
mysql -u root -p < DB.txt
```

#### 4. Add dataset files (if not present)

Ensure the following files exist in the `Dataset/` directory:

* `model.csv`
* `ecommerce.csv`

#### 5. Run the server

Double-click `run.bat` or run manually:

```bash
python Main.py
```

Open browser and navigate to:

```
http://127.0.0.1:5000/index
```

---

### 🤖 How It Works

1. **Signup/Login**: New users register and login.
2. **Browse Products**: View available items with prices and images.
3. **Negotiate via Chatbot**:

   * `Text`: Enter messages like `first price` or `final price`.
   * `Voice`: Record voice and send for negotiation.
4. **Purchase Product**: Confirm and place order.
5. **Post Review**: Leave feedback, analyzed for sentiment.
6. **View Orders/Reviews**: Track past purchases and sentiments.

> 💬 Keywords like `first price` and `final price` trigger price deductions. Other input returns a default “not trained” response.

---

### 📸 Screenshots

UI walkthrough and chatbot interactions are documented in `SCREENS.docx`. You can export them to PNG/JPG and upload to GitHub to link them here.

---

### 🚀 Sample Voice Interaction

1. Click “Voice Chatbot”
2. Start recording with microphone
3. Say: `first price` → chatbot offers 10% discount
4. Say: `final price` → chatbot offers additional 5% off
5. Click “Purchase” to complete the order

---

### 📊 Machine Learning Models

Used in `Main.py` and `test.py`:

* **Support Vector Regression (SVR)**: Predicts initial negotiation price.
* **KNN Regressor**: Refines the predicted price based on product similarity.
* Normalization using `MinMaxScaler`.

---

### ✅ To-Do for Deployment

* Add all datasets (`model.csv`, `ecommerce.csv`)
* Add product images to `static/img/`
* Install and link `ffmpeg` properly (for voice)
* (Optional) Dockerize app for easy deployment

---
