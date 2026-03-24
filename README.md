# 🚨 LifeGuard Emergency Network

A real-time emergency response PWA with patient monitoring, blood donor registry, hospital dispatch, and AI health assistant.

![LifeGuard](https://img.shields.io/badge/LifeGuard-Emergency%20Network-red?style=for-the-badge)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115-green?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-orange?style=flat-square)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🫀 Patient Dashboard | Live BPM monitor, anomaly simulation, SOS dispatch |
| 📳 Impact Detection | Accelerometer-based fall/crash detection |
| 🤖 Health AI | Gemini-powered symptom checker & appointment booking |
| 🩸 Blood Donor Registry | Emergency blood request feed with live updates |
| 🏥 Hospital Hub | Post blood signals, filter donors, view SOS alerts |
| 🚑 Fleet Management | Admin panel for ambulance registration |
| 📧 OTP Verification | Email-based account verification |
| 📱 PWA / APK | Installable on Android as a native-like app |

---

## 🚀 Quick Deploy (Railway — Free)

1. Fork this repository
2. Go to [railway.app](https://railway.app) → **New Project** → **Deploy from GitHub**
3. Select this repo
4. Add environment variables (see below)
5. Done — you get a live HTTPS URL

---

## 🔐 Environment Variables

Set these in Railway / Render / your `.env` file:

| Variable | Description | Where to get it |
|---|---|---|
| `GEMINI_API_KEY` | Google Gemini AI key | [aistudio.google.com](https://aistudio.google.com/app/apikey) |
| `SENDER_EMAIL` | Gmail address for OTP emails | Your Gmail |
| `SENDER_PASSWORD` | Gmail App Password | Google Account → Security → App Passwords |

> ⚠️ Never commit real keys to GitHub. Use `.env` locally (already in `.gitignore`).

---

## 💻 Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/lifeguard-emergency.git
cd lifeguard-emergency

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up environment variables
cp .env.example .env
# Edit .env and add your keys

# 5. Run the server
uvicorn main:app --reload --port 8000

# 6. Open browser
# http://localhost:8000
```

---

## 📱 Install as Android APK

### Method 1 — Install directly from browser (Easiest)
1. Open your deployed URL in **Chrome on Android**
2. Tap the **"Add to Home Screen"** banner or menu option
3. The app installs like a native APK ✅

### Method 2 — Build a real APK with Bubblewrap

```bash
# Prerequisites: Node.js, Android Studio
npm install -g @bubblewrap/cli

# Replace with your deployed URL
bubblewrap init --manifest https://YOUR_URL.railway.app/manifest.json
bubblewrap build
# Output: app-release-signed.apk
```

### Method 3 — GitHub Actions Auto-Build
1. Push a new release tag to this repo
2. GitHub Actions automatically builds the APK
3. Download from the **Releases** page

---

## 📁 Project Structure

```
lifeguard-emergency/
├── main.py                        # FastAPI app + frontend HTML
├── requirements.txt               # Python dependencies
├── Procfile                       # For Railway/Heroku
├── railway.toml                   # Railway config
├── render.yaml                    # Render config
├── .env.example                   # Environment variable template
├── .gitignore                     # Ignores secrets & build files
└── .github/
    └── workflows/
        └── deploy.yml             # Auto-deploy + APK build CI/CD
```

---

## 🔑 Default Login Credentials

| Role | Credential |
|---|---|
| Hospital Staff | Email must end in `@lifeguard.com` |
| Ambulance Admin | Username: `superadmin` / change password in `main.py` |

---

## 🛠 Tech Stack

- **Backend:** Python + FastAPI
- **Frontend:** Vanilla HTML/CSS/JS + TailwindCSS
- **Database:** Firebase Firestore
- **Auth:** Firebase Authentication
- **AI:** Google Gemini 2.5 Flash
- **Email:** Gmail SMTP
- **Hosting:** Railway / Render

---

## 📄 License

MIT License — free to use and modify.
