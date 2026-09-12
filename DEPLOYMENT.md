# DevForge Deployment Guide

This guide explains how to deploy **DevForge** to the cloud or run it in a unified single-port production mode.

---

## 🌟 Method 1: Deploy to Render (Recommended & Free)

[Render.com](https://render.com) provides free cloud hosting with native Docker support (which includes GCC, G++, Python, Java, and Node.js).

### Step-by-Step:
1. **Initialize a Git repository** (if not already done):
   ```bash
   cd C:\Users\Akhila\.gemini\antigravity\scratch\intelligent-dev-assistant
   git init
   git add .
   git commit -m "Initial commit of DevForge"
   ```
2. **Push to your GitHub account**:
   - Create a new public or private repository on [GitHub](https://github.com/new) called `devforge`.
   - Link and push your code:
     ```bash
     git remote add origin https://github.com/YOUR_USERNAME/devforge.git
     git branch -M main
     git push -u origin main
     ```
3. **Deploy on Render**:
   - Go to [dashboard.render.com](https://dashboard.render.com/) and sign in with GitHub.
   - Click **New +** -> **Web Service**.
   - Select your `devforge` GitHub repository.
   - Set **Environment** to `Docker`.
   - (Optional) In **Environment Variables**, add:
     - `GEMINI_API_KEY`: your Google Gemini API key
     - `PORT`: `5000`
   - Click **Create Web Service**.
4. **Done!** Render will build the container with all compilers and give you a live HTTPS URL (e.g. `https://devforge-assistant.onrender.com`).

---

## 🚀 Method 2: Deploy to Railway

[Railway.app](https://railway.app) automatically detects the `Dockerfile` and deploys it in minutes:

1. Push your project to GitHub (see Step 1 & 2 above).
2. Go to [Railway.app](https://railway.app) and click **New Project** -> **Deploy from GitHub repo**.
3. Select your `devforge` repository.
4. Add environment variable `GEMINI_API_KEY` (optional).
5. Click **Deploy**. Railway will give you a public URL (e.g. `https://devforge.up.railway.app`).

---

## 🐳 Method 3: Deploy with Docker (Any Cloud / VPS / AWS / Cloud Run)

You can run DevForge inside a lightweight container anywhere:

1. **Build the Docker image**:
   ```bash
   docker build -t devforge .
   ```
2. **Run the container**:
   ```bash
   docker run -d -p 5000:5000 -e GEMINI_API_KEY="your_key_here" devforge
   ```
3. Open `http://localhost:5000` in your browser.

---

## ⚡ Method 4: Production Mode on Localhost / Local Network

If you want to run the optimized production build locally on a single port (without the Vite dev server):

1. **Build the frontend bundle**:
   ```bash
   npm run build
   ```
2. **Start the production server**:
   ```bash
   npm run server
   ```
3. Open **`http://localhost:5000`** in your browser. Both the React frontend and Express backend will be served unified on port `5000`!
