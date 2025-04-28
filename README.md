# 🧠 Boterview

**Boterview** is a multilingual, AI-powered interview bot built using **AWS Chalice**, **OpenAI GPT**, **Gradio**, and **AWS Translate**. It conducts personalized interview sessions, generates insightful feedback, and manages session data using **DynamoDB**.

---

## 🌟 Features

- 📄 **Resume and Job Description Parsing**
- 🧠 **Skill Extraction using NLP**
- ❓ **Dynamic Question Generation based on Extracted Skills**
- 🌍 **Multilingual Translation of Questions and Feedback**
- 🔊 **Voice Input Support (via Whisper)**
- 🗣️ **Feedback with Confidence Estimation**
- 💾 **Session Saving and Retrieval (DynamoDB)**

---

## 🧰 Tech Stack

- **Python 3.12+**
- **AWS Chalice**
- **Gradio**
- **OpenAI API**
- **AWS Services**:
  - DynamoDB
  - Translate
  - Polly
- **Whisper** (local)
- **dotenv**

---

## ⚙️ Setup Instructions

### 1. Create Virtual Environment & Install Dependencies

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

OPENAI_API_KEY=your_openai_api_key
AWS_REGION=your_aws_region

cd ~/interview-bot/api
source ../venv/bin/activate
chalice local --host 0.0.0.0 --port 8000

cd ~/interview-bot
source venv/bin/activate
python frontend_ui.py

💾 Session Management
After each interview:

A unique Session ID will be generated (e.g., d2980647-2122-4286-ba22-81973e6a8ce0)
Use this ID in the "Session Retrieval" tab to reload past sessions, including:
Resume and Job Description
Generated Questions
Your Answers
AI Feedback (with translation if enabled)


📂 Folder Structure Suggestion
bash
Copy
Edit
interview-bot/
│
├── api/                  # AWS Chalice backend
├── utils/                # Utility scripts and helpers
├── venv/                 # Python virtual environment
├── frontend_ui.py        # Gradio-based UI
├── requirements.txt
└── .env            
