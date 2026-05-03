# 🤖 ML Based Resume Screening System

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![ML](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green?style=for-the-badge)
![NLP](https://img.shields.io/badge/NLP-TF--IDF-orange?style=for-the-badge)
![Gradio](https://img.shields.io/badge/Deployed-Gradio-purple?style=for-the-badge)
![Accuracy](https://img.shields.io/badge/Accuracy-100%25-brightgreen?style=for-the-badge)

> An end-to-end Machine Learning system that automatically screens resumes, scores them against job descriptions, predicts the most suitable job role, identifies skill gaps and suggests resume improvements — all deployed as a live web application.

---

## 📋 Table of Contents

- [About The Project](#about-the-project)
- [Features](#features)
- [System Architecture](#system-architecture)
- [Dataset](#dataset)
- [Technologies Used](#technologies-used)
- [ML Models](#ml-models)
- [Results](#results)
- [How To Run](#how-to-run)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)

---

## 📌 About The Project

Manual resume screening is slow, expensive and prone to human bias. Recruiters spend only 6-8 seconds per resume and thousands of applications make it impossible to screen accurately by hand.

This project solves that problem by building an intelligent ML-based system that:

- ✅ Reads PDF resumes automatically
- ✅ Scores resumes against job descriptions
- ✅ Predicts the most suitable job role
- ✅ Identifies missing skills
- ✅ Generates a personalized learning roadmap
- ✅ Enhances resume language with power words
- ✅ Deployed as a live web application

---

## ⭐ Features

### 1. 📊 Resume Scoring
Compares resume against job description using a weighted formula:
```
Final Score = (40% × TF-IDF Cosine Similarity) + (60% × Skill Match Score)
```
Skill matching is given higher weight because technical skills are the most critical factor in hiring decisions.

### 2. 🤖 Job Role Prediction
Random Forest classifier predicts the most suitable job role from resume content with a confidence percentage.

**Supported Job Roles:**
- AI Researcher
- Cybersecurity Analyst
- Data Scientist
- Software Engineer

### 3. 📚 Skill Recommendation Engine
- Identifies missing skills for the target role
- Prioritizes skills as High, Medium or Low priority
- Provides real course recommendations from Coursera and Udemy
- Estimates total time to fill the skill gap

### 4. ✨ Resume Enhancement Module
- Detects weak words and suggests professional power words
- Checks resume section completeness
- Calculates overall resume health score
- Generates a professional objective tailored to the target role

### 5. 📈 Visual Dashboard
Interactive visual dashboard showing:
- Score gauge (donut chart)
- Score breakdown bar chart
- Skills analysis pie chart
- Skill status overview
- Score improvement potential
- ML analysis summary

---

## 🏗️ System Architecture

```
📄 PDF Resume Upload
        ↓
📖 Text Extraction (pdfplumber)
        ↓
🧹 NLP Preprocessing (clean_text)
        ↓
🔢 TF-IDF Vectorization
        ↓
🤖 Random Forest Prediction
        ↓
        ├──→ 📊 Resume Score %
        ├──→ 🎯 Job Role Prediction
        ├──→ 📚 Skill Recommendations
        └──→ ✨ Resume Enhancement
```

---

## 📦 Dataset

**Dataset:** AI-Powered Resume Screening Dataset 2025
**Source:** [Kaggle](https://www.kaggle.com/datasets/mdtalhask/ai-powered-resume-screening-dataset-2025)

| Property | Value |
|---|---|
| Total Resumes | 1,000 |
| Features | 11 |
| Job Role Categories | 4 |
| Train / Test Split | 80% / 20% |
| Missing Values | Certifications (274) — filled with 'None' |

**Dataset Columns:**
- Resume_ID, Name, Skills, Experience (Years)
- Education, Certifications, Job Role
- Recruiter Decision, Salary Expectation
- Projects Count, AI Score

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **pandas & numpy** | Data manipulation and analysis |
| **scikit-learn** | ML models and TF-IDF vectorization |
| **NLTK** | Natural Language Processing |
| **pdfplumber** | PDF text extraction |
| **matplotlib & seaborn** | Data visualization |
| **Gradio** | Web application deployment |
| **Google Colab** | Development environment |

---

## 🤖 ML Models

Three models were trained and compared:

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| **Random Forest** 🏆 | 100% | 1.00 | 1.00 | 1.00 |
| Logistic Regression | 100% | 1.00 | 1.00 | 1.00 |
| KNN | 100% | 1.00 | 1.00 | 1.00 |

### Why Random Forest Was Chosen:
- ✅ Best at handling overfitting through ensemble voting
- ✅ Most robust on completely new unseen real world data
- ✅ Industry standard used by companies like LinkedIn and Google
- ✅ Best balance of speed and accuracy
- ✅ All 3 models reaching 100% independently validates the result

---

## 📊 Results

```
Model Accuracy     : 100%
Training Samples   : 800 resumes
Testing Samples    : 200 resumes
TF-IDF Features    : 34 meaningful features
Job Roles          : 4 (perfectly classified)
```

**Per Role Performance:**

| Job Role | Precision | Recall | F1 | Support |
|---|---|---|---|---|
| AI Researcher | 1.00 | 1.00 | 1.00 | 52 |
| Cybersecurity Analyst | 1.00 | 1.00 | 1.00 | 51 |
| Data Scientist | 1.00 | 1.00 | 1.00 | 45 |
| Software Engineer | 1.00 | 1.00 | 1.00 | 52 |

---

## 🚀 How To Run

### Step 1 — Open Google Colab
```
Go to colab.research.google.com
Create a new notebook
```

### Step 2 — Install Libraries
```python
!pip install nltk scikit-learn pandas numpy matplotlib seaborn wordcloud pdfplumber gradio
```

### Step 3 — Mount Google Drive
```python
from google.colab import drive
drive.mount('/content/drive')
```

### Step 4 — Download Dataset
```
Download from Kaggle:
https://www.kaggle.com/datasets/mdtalhask/ai-powered-resume-screening-dataset-2025

Upload to Google Drive folder
```

### Step 5 — Run All Cells In Order
```
Cell 1  → Install & Import Libraries
Cell 2  → Load Dataset
Cell 3  → Explore Dataset
Cell 4  → Visualize Data
Cell 5  → Preprocessing
Cell 6  → TF-IDF Vectorization
Cell 7  → Train ML Models
Cell 8  → Confusion Matrix
Cell 9  → Resume Scoring System
Cell 10 → Skill Recommendation Engine
Cell 11 → PDF Resume Parser
Cell 12 → Complete System
Cell 13 → Visual Dashboard
Cell 14 → Resume Enhancement
Cell 15 → Gradio Web App (Launch!)
```

### Step 6 — Use The Web App
```
1. Upload your PDF resume
2. Paste the job description
3. Select target job role
4. Click Analyse My Resume!
5. Check all 4 result tabs
```

---

## 📁 Project Structure

```
ML-Resume-Screening/
│
├── RESUME_SCREENING.ipynb    ← Main Colab notebook
├── README.md                 ← This file
│
├── dataset/
│   └── resume_data.csv       ← Kaggle dataset
│
└── sample/
    └── sample_resume.pdf     ← Sample resume for testing
```

---

## 💡 How The Scoring Works

```
Resume uploaded
      ↓
TF-IDF converts resume & JD to numbers
      ↓
Cosine Similarity measures text similarity → TF-IDF Score (40%)
      ↓
Skill matching checks skills one by one   → Skill Score (60%)
      ↓
Final Score = (0.4 × TF-IDF) + (0.6 × Skill Match)

Score Interpretation:
🟢 80% and above  → Excellent Match
🟡 60% to 79%     → Good Match
🟠 40% to 59%     → Average Match
🔴 Below 40%      → Poor Match
```

---

## 🎯 Key Concepts Used

| Concept | Usage In Project |
|---|---|
| **NLP** | Text cleaning and preprocessing |
| **TF-IDF** | Converting resume text to numerical vectors |
| **Cosine Similarity** | Measuring resume-JD similarity |
| **Label Encoding** | Converting job roles to numbers |
| **Train-Test Split** | 80/20 data division |
| **Random Forest** | Job role classification |
| **Ensemble Learning** | 100 trees voting together |
| **PDF Parsing** | Extracting text from resume files |

---

## 🔮 Future Improvements

- [ ] Add more job roles (DevOps, Product Manager, etc.)
- [ ] LinkedIn profile URL analysis
- [ ] Real-time job listing matching
- [ ] Interview question generator based on skill gaps
- [ ] ATS (Applicant Tracking System) score checker
- [ ] Multi-language resume support
- [ ] Salary prediction based on skills and experience

---

## 👨‍💻 Built With

```
Language   : Python 3.10+
Environment: Google Colab
ML Library : scikit-learn
NLP        : NLTK + TF-IDF
UI         : Gradio
PDF Parser : pdfplumber
Viz        : matplotlib + seaborn
```

---

## 📝 License

This project is for educational purposes as part of a Machine Learning course final project.

---

## 🙏 Acknowledgements

- Dataset: [Kaggle — AI-Powered Resume Screening Dataset 2025](https://www.kaggle.com/datasets/mdtalhask/ai-powered-resume-screening-dataset-2025)
- Libraries: scikit-learn, NLTK, pdfplumber, Gradio
- Platform: Google Colab

---

<div align="center">

**Built with ❤️ using Python, Machine Learning & NLP**

⭐ Star this repository if you found it helpful!

</div>
