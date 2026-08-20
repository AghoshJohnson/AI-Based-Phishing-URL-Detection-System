PhishDefend – AI-Powered Phishing URL Detection

Live demo: https://ai-phishing-url-detector-rdzx.onrender.com/

PhishDefend is a machine learning web app that scans any URL and classifies it as legitimate or phishing, along with a confidence score. It analyzes a URL the way a security analyst would — structure, domain history, and page behavior — and returns an instant verdict through a clean, cyberpunk-themed interface.

Table of Contents
Features
How It Works
Project Structure
Getting Started
Usage
Tech Stack
Limitations
Roadmap
License
Features
Instant URL scanning — paste any URL and get a phishing/legitimate verdict
Confidence score — see how certain the model is about its prediction
Multi-signal analysis — combines lexical, domain, and page-behavior features
Cyber-themed UI — responsive Bootstrap 5 interface with live scan animations
Single-endpoint Flask app — lightweight and easy to deploy
How It Works

User submits URL → Flask route (app.py) → Feature extraction (featureExtractor.py + extractorFunctions.py):

Address-bar features: URL length, depth, shortener detection, prefix/suffix, dot count, sensitive keywords
Domain-based features: WHOIS domain age & expiration window
HTML/JS behavior features: iframe usage, mouseover tricks, redirect chains → compressed via PCA into one signal
Symbol-based flags: IP address in URL, "@" symbol, unicode/IDN homograph tricks

These feed into the PyCaret classification model (phishingdetection.pkl), which returns a prediction label and confidence score rendered in index.html.

Project Structure

PhishDefend/
app.py — Flask web app (main entry point)
main.py — CLI script for testing predictions locally
featureExtractor.py — Combines all extracted features into a model-ready row
extractorFunctions.py — Individual feature extraction functions
model/
phishingdetection.pkl — Trained PyCaret classification pipeline
pca_model.pkl — PCA model for HTML/JS behavior features
templates/
index.html — Frontend UI (Bootstrap 5 + custom cyber theme)
requirements.txt — Python dependencies
README.md

Getting Started

Prerequisites: Python 3.10+, pip

Installation:

git clone https://github.com/<your-username>/PhishDefend.git
cd PhishDefend
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
pip install -r requirements.txt

Run locally:

python app.py

The app will start on http://127.0.0.1:5000/ by default.

Run a quick CLI test:

python main.py

This runs a few sample URLs (known phishing and legitimate) through the model and prints the predictions to the console.

Usage
Open the app in your browser (locally or via the live demo).
Paste a URL into the Target URL field.
Click Scan.
View the verdict — Secure (green) or Threat detected (red) — along with the model's confidence percentage.
Tech Stack
Backend: Flask (Python)
ML Pipeline: PyCaret (classification), scikit-learn (PCA)
Feature Data: whois, httpx, pandas, re
Frontend: HTML5, Bootstrap 5, Bootstrap Icons
Deployment: Render
Limitations
Domain-age features rely on live WHOIS lookups, which can be slow or unavailable for some registrars — this adds latency to each scan.
HTML/JS behavior features require fetching the live page, so scans of unreachable, slow, or bot-blocking sites may be less accurate.
The model is trained on a fixed dataset and may not catch the newest phishing patterns (e.g. novel typosquatting or homograph techniques) until retrained.
Roadmap
Browser extension for real-time scanning without copy-pasting URLs
Caching layer for WHOIS/HTTP lookups to speed up repeat scans
Expanded training data covering newer phishing patterns
Public API endpoint for programmatic/bulk URL checks
License

This project was built for hackathon submission purposes. Add your preferred license here (e.g. MIT) if you plan to open-source it.

Live demo: https://ai-phishing-url-detector-rdzx.onrender.com/
