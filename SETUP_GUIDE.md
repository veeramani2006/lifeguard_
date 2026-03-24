# 📋 Step-by-Step GitHub Setup Guide

Follow these exact steps to upload LifeGuard to GitHub.

---

## STEP 1 — Create GitHub Account & Repo

1. Go to **github.com** → Sign up (or log in)
2. Click the **+** icon (top right) → **New repository**
3. Fill in:
   - Repository name: `lifeguard-emergency`
   - Description: `LifeGuard Emergency Network`
   - Visibility: **Public** (required for free Railway deploy)
   - ✅ Check **Add a README file**
4. Click **Create repository**

---

## STEP 2 — Upload All Files

### Option A: Drag & Drop (No coding needed)
1. Open your new repo on GitHub
2. Click **Add file** → **Upload files**
3. Drag ALL files from this folder into the upload area:
   - `main.py`
   - `requirements.txt`
   - `Procfile`
   - `railway.toml`
   - `render.yaml`
   - `.env.example`
   - `.gitignore`
   - `README.md`
4. For the `.github/workflows/deploy.yml` file:
   - Click **Add file** → **Create new file**
   - Type the name: `.github/workflows/deploy.yml`
   - Paste the content from the file
5. Commit message: `Initial commit - LifeGuard Emergency Network`
6. Click **Commit changes**

### Option B: Git Commands (If you have Git installed)
```bash
cd lifeguard-emergency   # this folder
git init
git add .
git commit -m "Initial commit - LifeGuard Emergency Network"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/lifeguard-emergency.git
git push -u origin main
```

---

## STEP 3 — Deploy to Railway (Get a Live URL)

1. Go to **railway.app** → Login with GitHub
2. Click **New Project** → **Deploy from GitHub repo**
3. Select `lifeguard-emergency`
4. Click **Variables** tab → Add these one by one:

   | Key | Value |
   |-----|-------|
   | `GEMINI_API_KEY` | Your Gemini key |
   | `SENDER_EMAIL` | your@gmail.com |
   | `SENDER_PASSWORD` | Your Gmail app password |

5. Click **Deploy** — wait ~2 minutes
6. Click **Settings** → **Domains** → **Generate Domain**
7. Your app is live at: `https://lifeguard-emergency-xxxx.railway.app`

---

## STEP 4 — Add GitHub Secrets (For APK Auto-Build)

1. In your GitHub repo → **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret** and add:

   | Secret Name | Value |
   |-------------|-------|
   | `RAILWAY_TOKEN` | From Railway → Account Settings → Tokens |
   | `APP_URL` | Your Railway URL (e.g. `https://lifeguard-xxxx.railway.app`) |

---

## STEP 5 — Build the APK

### Quick way (Chrome on Android):
1. Open your Railway URL on your Android phone in Chrome
2. Chrome shows a banner: **"Add to Home Screen"**
3. Tap it → installed like an app! ✅

### Real APK way:
1. Go to your GitHub repo → **Releases** → **Create a new release**
2. Tag: `v1.0.0`
3. Click **Publish release**
4. GitHub Actions runs automatically and builds the APK
5. Download from the release page when done (~10 minutes)

---

## ✅ You're Done!

Your LifeGuard app is now:
- ✅ On GitHub (version controlled)
- ✅ Live on the internet (Railway)
- ✅ Installable as an Android app
