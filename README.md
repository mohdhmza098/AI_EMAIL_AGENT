<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:071426,45:1261FE,100:00D4FF&height=190&section=header&text=AI%20Email%20Campaign%20Agent&fontSize=32&fontColor=FFFFFF&fontAlignY=38&desc=Customer%20Analytics%20%7C%20Generative%20AI%20%7C%20Personalization&descSize=13&descAlignY=61" width="100%" alt="AI Email Campaign Agent"/>

# AI Email Campaign Automation Agent

### Turn Customer Data into Personalized Marketing Drafts with AI

**Developed by Mohd Hamza**

<br>

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
<img src="https://img.shields.io/badge/OpenRouter-AI%20API-7057FF?style=for-the-badge" alt="OpenRouter"/>
<img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"/>
<img src="https://img.shields.io/badge/IBM%20Bob-AI%20Coding%20Assistant-1261FE?style=for-the-badge&logo=ibm&logoColor=white" alt="IBM Bob"/>

</div>


---

## ✦ Project Overview

Marketing teams need relevant messages, but writing individual emails for every customer takes time.

This project combines **customer analytics and generative AI** to create personalized marketing email drafts through a simple Streamlit application.

## ⚡ Intelligent Workflow

<div align="center">

<img src="![AI Email Campaign Workflow](project_workflow.png)" width="100%" alt="AI Email Campaign Automation Workflow"/>

</div>

**Workflow:** Upload customer data → Process and analyze → Segment customers → Generate personalized emails → Review and download → Save campaign history.

## 🚀 Key Features

* **Smart Segmentation:** Categorizes customers into High, Medium, and Low value groups.
* **AI Email Generation:** Creates personalized email subjects and content using customer context.
* **Flexible Tone Selection:** Professional, Friendly, and Urgent.
* **Customer Analytics:** Explores spending patterns, income distribution, and customer segments.
* **Campaign History:** Stores generated emails in a SQLite database.
* **Easy Export:** Downloads individual email drafts and campaign history.

## 🧠 Customer Analytics

| Feature         | Calculation                     |
| --------------- | ------------------------------- |
| Total Purchases | Web + Catalog + Store purchases |
| Total Spent     | Sum of product spending columns |
| Customer Value  | Total Spent × Total Purchases   |

**Customer Segments**

* 🟢 **High:** Customer Value ≥ 15,000
* 🟡 **Medium:** Customer Value ≥ 5,000 and < 15,000
* 🔴 **Low:** Customer Value < 5,000

## 🛠️ Technology Stack

| Technology            | Purpose                            |
| --------------------- | ---------------------------------- |
| Python                | Application logic and calculations |
| Pandas                | Customer data processing           |
| Streamlit             | Interactive web interface          |
| OpenRouter API        | AI model integration               |
| OpenAI-compatible SDK | API communication                  |
| SQLite                | Campaign history storage           |
| IBM Bob               | AI-assisted development            |

## ▶️ Run the Project

**1. Clone the repository**

```bash
git clone https://github.com/sarishadeel206/AI_Email_Campaign_Agent.git
cd AI_Email_Campaign_Agent
```

**2. Install dependencies**

```bash
pip install -r requirements.txt
```

**3. Configure your API key**

Create a `.env` file in the project root:

```env
OPENROUTER_API_KEY=your_api_key_here
```

**4. Start the application**

```bash
streamlit run app.py
```

Never upload your `.env` file, API keys, or private customer data to GitHub.

## 🤖 IBM Bob Integration

IBM Bob was used as an AI coding assistant to support project planning, implementation, data-processing logic, testing, and documentation.

This project demonstrates how AI-assisted development can help transform an idea into a practical application.

## 🔭 Future Scope

* Bulk email generation
* A/B testing for email subject lines
* Advanced customer segmentation
* Scheduled campaigns and email delivery
* Cloud deployment and authentication

> **Current scope:** The application generates and stores email drafts for review. It does not automatically send emails.

---

<div align="center">

### Customer Data × Generative AI × Smart Automation

**AI Email Campaign Automation Agent**

<sub>Built with Python, data analytics, and AI-assisted development.</sub>

</div>
