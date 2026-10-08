# 🥗 MacroSnap — AI Nutrition Buddy

MacroSnap is an AI-powered nutrition assistant built with **Streamlit, Google Gemini, and Twilio WhatsApp**.

It allows users to describe a meal or upload a meal photo and receive an estimated calorie and macronutrient breakdown. Users can also set a daily calorie goal and track their calorie consumption in real time.

## 🚀 Live Demo

**Streamlit App:** https://macrosnap-re8ej6bhc2x4hbdbzenhli.streamlit.app/

## 📌 Features

* 🥗 AI-powered meal analysis
* 💬 Text-based meal descriptions
* 📸 Meal photo analysis using Gemini Vision
* 🔥 Estimated calorie calculation
* 💪 Protein, carbohydrate, and fat estimation
* 🎯 Daily calorie goal
* 📊 Live consumed and remaining calorie tracker
* 📱 Send nutrition summary to WhatsApp
* 🔐 API keys stored securely using Streamlit Secrets

## ⭐ Original Feature

### Daily Calorie Goal + Live Calorie Tracker

I extended the original MacroSnap application by adding a personalized daily calorie goal and live calorie tracking system.

The user sets a daily calorie target, for example:

```text
Daily Goal: 2000 kcal
```

After every meal analysis, the application extracts the estimated calorie value from Gemini's response and updates:

```text
Consumed Calories
Remaining Calories
```

For example:

```text
Daily Goal: 2000 kcal
Consumed: 680 kcal
Remaining: 1320 kcal
```

This feature works with both **text meal descriptions and uploaded meal photos**.

## 🧠 How It Works

```text
User
  │
  ├── Types meal description
  │          OR
  └── Uploads meal photo
             │
             ▼
       Streamlit App
             │
             ▼
        Google Gemini
             │
             ▼
   Nutrition estimation
   ├── Calories
   ├── Protein
   ├── Carbohydrates
   └── Fat
             │
             ▼
      Calorie Tracker
   ├── Consumed calories
   └── Remaining calories
             │
             ▼
       Twilio WhatsApp
             │
             ▼
       User receives
      nutrition summary
```

## 🛠️ Technologies Used

* Python
* Streamlit
* Google Gemini API
* Twilio WhatsApp API
* Git
* GitHub
* Visual Studio Code

## 📂 Project Structure

```text
MacroSnap/
│
├── app.py
├── prompts.py
├── requirements.txt
├── README.md
├── .gitignore
│
└── .streamlit/
    └── secrets.toml.example
```

> The actual `secrets.toml` file is intentionally excluded from GitHub.

## 🔐 Environment Variables / Secrets

MacroSnap uses Streamlit Secrets for sensitive credentials.

Required secrets:

```toml
GEMINI_API_KEY = "your-gemini-api-key"
TWILIO_ACCOUNT_SID = "your-twilio-account-sid"
TWILIO_AUTH_TOKEN = "your-twilio-auth-token"
TWILIO_WHATSAPP_FROM = "whatsapp:+14155238886"
TWILIO_CONTENT_SID = "your-twilio-content-template-sid"
```

Never commit real API keys or authentication tokens to GitHub.

## ▶️ Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/Banothu-Nithin/MacroSnap.git
cd MacroSnap
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Streamlit Secrets

Create:

```text
.streamlit/secrets.toml
```

and add your own API credentials.

### 6. Run the application

```bash
streamlit run app.py
```

The application will open in your browser.

## 📊 Example

A user enters:

```text
I ate 2 eggs and 2 slices of bread.
```

Gemini provides an estimated nutrition breakdown.

MacroSnap then updates the tracker:

```text
Daily Goal: 2000 kcal
Consumed: 300 kcal
Remaining: 1700 kcal
```

After another meal containing approximately 380 kcal:

```text
Daily Goal: 2000 kcal
Consumed: 680 kcal
Remaining: 1320 kcal
```

The complete nutrition summary can then be sent to the user's WhatsApp.

## ⚠️ Disclaimer

MacroSnap provides **AI-generated nutritional estimates**, not medical or dietary advice. Actual calories and macronutrients can vary depending on ingredients, portion sizes, preparation methods, and brands.

## 👨‍💻 Developer

**Nithin Banothu**

B.Tech Electronics and Communication Engineering

Interested in Python, AI Applications, Full-Stack Development, Automation, and Generative AI.

## 📄 License

This project is intended for educational and portfolio purposes.
