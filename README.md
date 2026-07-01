📌 Project Overview

CyberGuard is an AI-powered web application that helps users identify phishing websites before visiting them. The system analyzes website URLs using machine learning and multiple security-related features to determine whether a website is legitimate or potentially malicious.

The application provides real-time predictions with confidence scores through a modern cybersecurity dashboard, helping users avoid phishing attacks and improve online safety.

🚨 Problem Statement

Phishing websites are one of the most common cyber threats used to steal user credentials, banking information, and personal data. Many users cannot distinguish between legitimate and fake websites because phishing pages often closely resemble trusted websites.

Existing solutions may require browser extensions or paid security software, making them less accessible for general users.

💡 Solution Overview

CyberGuard uses Machine Learning to analyze URLs based on several phishing indicators such as:

URL length
Domain age
Number of dots
URL depth
URL shortening services
Sensitive keywords
Unicode characters
Domain information
HTML behavior
Redirect analysis

The extracted features are processed by a trained machine learning model to classify URLs as either:

✅ Safe
🚨 Phishing

along with a prediction confidence score.

✨ Features
🤖 AI-powered phishing detection
🌐 Real-time URL analysis
📊 Confidence score prediction
🛡️ Safe / Phishing classification
⚡ Fast Flask web application
🎨 Modern cybersecurity dashboard
🔍 URL feature extraction
💻 Responsive user interface
🛠 Technology Stack
Frontend
HTML5
CSS3
Bootstrap 5
JavaScript
Backend
Python
Flask
Machine Learning
PyCaret
Scikit-learn
Pandas
NumPy
Other Libraries
HTTPX
WHOIS
urllib
Regex (re)
⚙️ Installation
Clone the repository
git clone https://github.com/yourusername/CyberGuard.git
Navigate into the project
cd CyberGuard
Create Virtual Environment

Windows

python -m venv venv

Activate

venv\Scripts\activate
Install dependencies
pip install -r requirements.txt
Run the application
python app.py
Open in Browser
http://127.0.0.1:5000
🚀 Usage Guide
Open the application.
Enter a website URL.
Click Scan.
Wait for the AI analysis.
View the prediction result.
Check whether the URL is Safe or Phishing.
Review the confidence score.
🎯 Future Scope
🌍 Live threat intelligence integration
🔗 VirusTotal API support
🌐 Browser extension
📱 Mobile application
📊 Threat analytics dashboard
📁 Scan history
📄 PDF report generation
🔐 User authentication
☁️ Cloud deployment
🧠 Deep Learning-based phishing detection
