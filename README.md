<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:071A2F,40:1261FE,100:00D4FF&height=200&section=header&text=AI%20EMAIL%20CAMPAIGN%20AGENT&fontSize=30&fontColor=FFFFFF&fontAlignY=38&desc=INTELLIGENT%20CUSTOMER%20PERSONALIZATION&descSize=14&descAlignY=60" width="100%" alt="AI Email Campaign Agent"/>

Turning Customer Data into Smarter Marketing with AI

Developed by Mohd Hamza

<br>

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/> <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"/> <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/> <img src="https://img.shields.io/badge/OpenRouter-AI%20Integration-7057FF?style=for-the-badge" alt="OpenRouter"/> <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"/> <img src="https://img.shields.io/badge/IBM%20Bob-AI%20Development-1261FE?style=for-the-badge&logo=ibm&logoColor=white" alt="IBM Bob"/>

</div>

✦ Project Overview

An AI-powered marketing application that analyzes customer behaviour, categorizes customers by value, and generates personalized email drafts using customer-specific information.

The project combines data analytics, generative AI, and application development in one simple interface.

◈ The Challenge

Generic marketing emails often overlook individual customer preferences and purchase behaviour. Writing personalized messages manually also takes time.

Our solution: Use customer data and AI to make email creation faster, more relevant, and easier to manage.

⬡ Intelligent Workflow
flowchart TD
    A(["📂 CUSTOMER DATA<br/>Upload CSV"]) --> B["⚙️ DATA PROCESSING<br/>Python + Pandas"]
    B --> C["📊 CUSTOMER ANALYTICS<br/>Spending & Purchases"]
    C --> D{"CUSTOMER VALUE<br/>SEGMENTATION"}
    D --> E["🟢 High Value"]
    D --> F["🟡 Medium Value"]
    D --> G["🔴 Low Value"]
    E --> H["🤖 AI EMAIL GENERATION"]
    F --> H
    G --> H
    H --> I["✉️ Personalized Email Draft<br/>OpenRouter API"]
    I --> J[("🗄️ SQLite<br/>Campaign History")]
    I --> K(["⬇️ Review & Download"])
    C -.-> L["📈 Analytics Dashboard"]
    J -.-> M["📋 View History / Export CSV"]

    classDef input fill:#102A43,stroke:#00D4FF,color:#FFFFFF,stroke-width:2px
    classDef process fill:#123C69,stroke:#4DA3FF,color:#FFFFFF,stroke-width:1.5px
    classDef ai fill:#3C2678,stroke:#A78BFA,color:#FFFFFF,stroke-width:2px
    classDef output fill:#075E54,stroke:#34D399,color:#FFFFFF,stroke-width:2px
    class A input
    class B,C,D,E,F,G,L process
    class H,I ai
    class J,K,M output
✧ Key Features
Smart Segmentation — Classifies customers into Low, Medium, and High value tiers.
AI-Powered Emails — Generates personalized subject lines and email content.
Flexible Tone Selection — Professional, Friendly, or Urgent.
Customer Analytics — Explore spending patterns, income distribution, and segments.
Campaign History — Stores generated emails using SQLite.
Easy Export — Download email drafts and export campaign records.
⚡ Technology Architecture
Technology	Role
Python	Application logic and feature engineering
Pandas	Customer data processing
Streamlit	Interactive web interface
OpenRouter API	AI-powered email generation
OpenAI-compatible SDK	Communication with the configured AI model
SQLite	Local campaign history
IBM Bob	AI-assisted development
▶ Run the Project

1. Clone the repository

git clone https://github.com/sarishadeel206/AI_Email_Campaign_Agent.git
cd AI_Email_Campaign_Agent

2. Install dependencies

pip install -r requirements.txt

3. Configure your API key

Create a .env file:

OPENROUTER_API_KEY=your_api_key_here

4. Launch the application

streamlit run app.py
🤖 IBM Bob Integration

IBM Bob was used as an AI coding assistant to support project planning, code implementation, data-processing logic, testing, and documentation.

This project demonstrates how AI-assisted development can help transform an idea into a practical application.

🚀 Future Enhancements
Bulk email generation
A/B testing for subject lines
Advanced customer segmentation
Scheduled campaigns and email delivery
Cloud deployment and user authentication

Current capability: Generates and stores email drafts. Automatic email delivery is planned as a future enhancement.

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:071A2F,100:1261FE&height=3&section=header" width="100%" alt=""/>

Built with Python · Data Analytics · Generative AI

MOHD HAMZA
AI Email Campaign Automation Agent

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00D4FF,50:1261FE,100:071A2F&height=100&section=footer" width="100%" alt="Decorative footer"/>

</div>
