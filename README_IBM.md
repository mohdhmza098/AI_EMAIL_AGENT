::: {align="center"}
`<img src="https://capsule-render.vercel.app/api?type=waving&color=0:071A2F,45:0F6CBD,100:00D4FF&height=220&section=header&text=AI%20Email%20Campaign%20Agent&fontSize=38&fontColor=FFFFFF&animation=fadeIn&fontAlignY=38&desc=Customer%20Analytics%20%7C%20Generative%20AI%20%7C%20Smart%20Personalization&descAlignY=60&descSize=15" width="100%" alt="Project banner"/>`{=html}

`<img src="https://img.shields.io/badge/IBM%20BOB-AI%20CODING%20ASSISTANT-1261FE?style=for-the-badge&logo=ibm&logoColor=white" alt="IBM Bob"/>`{=html}
`<img src="https://img.shields.io/badge/STREAMLIT-WEB%20APP-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"/>`{=html}
`<img src="https://img.shields.io/badge/OPENROUTER-GENERATIVE%20AI-6B4EFF?style=for-the-badge" alt="OpenRouter"/>`{=html}
`<img src="https://img.shields.io/badge/PYTHON-DATA%20PROCESSING-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>`{=html}

### Turn customer data into personalized marketing emails --- powered by AI.

A lightweight Streamlit application that explores customer behaviour,
segments customers by value, generates tailored email drafts with an
LLM, and stores campaign history locally.
:::

------------------------------------------------------------------------

## ✨ Project Overview

  -----------------------------------------------------------------------
  🎯 Objective                        ⚡ Workflow
  ----------------------------------- -----------------------------------
  Reduce manual effort and make       Upload CSV → choose segment and
  marketing emails more relevant to   customer → select tone → generate
  each customer.                      email → save history.

  -----------------------------------------------------------------------

**Dataset:** Customer Personality Analysis --- 2,240 rows and 29
columns.

## 🚨 Problem Statement

Marketing teams face two common challenges:

-   **Scale:** Writing personalized emails for every customer takes
    time.
-   **Relevance:** Generic bulk emails may ignore customer spending,
    purchase history, and income profiles.

This project combines customer-data analysis and AI-assisted drafting in
one lightweight application without requiring a full CRM setup.

## 💡 Solution

-   **Segment** customers into Low, Medium, and High value tiers.
-   **Generate** customer-aware email drafts using an LLM and a selected
    tone.
-   **Persist** generated emails in a local SQLite database with
    timestamps.
-   **Visualize** customer segments, spending patterns, income
    distribution, and dataset summaries.
-   **Export** individual email drafts and campaign history.

> **Current scope:** The application generates drafts for review; it
> does not automatically send emails.

## 🖥️ Application Workflow

``` mermaid
flowchart TD
    A[Upload customer CSV] --> B[Load and enrich data]
    B --> C[Calculate customer features]
    C --> D{Choose workspace}
    D --> E[Campaign Generator]
    E --> F[Select segment, customer and tone]
    F --> G[Build contextual prompt]
    G --> H[OpenRouter LLM API]
    H --> I[Display and download draft]
    I --> J[(Save to SQLite history)]
    D --> K[Analytics Dashboard]
    K --> L[Segment, spending and income charts]
    D --> M[History]
    M --> N[Review records or export CSV]
```

## 🚀 Key Features

  -----------------------------------------------------------------------
  Feature                             Description
  ----------------------------------- -----------------------------------
  🧩 **Three-tier segmentation**      Low / Medium / High tiers based on
                                      `Customer_Value`.

  ✉️ **AI email generation**          Generates a subject line and email
                                      body using customer context.

  🎚️ **Selectable tone**              Professional, Friendly, or Urgent.

  🔎 **Segment filtering**            Filter the customer list before
                                      selecting a customer.

  👤 **Customer detail card**         ID, income, total spending, total
                                      purchases, and segment.

  📈 **Analytics dashboard**          Segment distribution, average
                                      spending by segment, income
                                      histogram, and summary statistics.

  🗂️ **Campaign history**             Stores generated email records in
                                      SQLite with timestamps.

  ⬇️ **Downloads and export**         Download an email as TXT or export
                                      history as CSV.

  🛡️ **Flexible CSV loading**         Attempts tab-separated input first,
                                      then comma-separated input.
  -----------------------------------------------------------------------

## 🧮 Customer Segmentation Logic

The application derives these features:

  Feature             Calculation
  ------------------- ----------------------------------------------
  `Age`               `2026 - Year_Birth`
  `Total_Purchases`   Web + Catalog + Store purchases
  `Total_Spent`       Sum of the product spending columns (`Mnt*`)
  `Customer_Value`    `Total_Spent × Total_Purchases`

``` python
Customer_Value >= 15000  # High
Customer_Value >= 5000   # Medium
Customer_Value < 5000    # Low
```

The segment label is included in the AI prompt to help tailor the email
content.

## 🧰 Technology Stack

::: {align="center"}
`<img src="https://skillicons.dev/icons?i=python,sqlite,jupyter,github" alt="Python, SQLite, Jupyter, GitHub" height="58"/>`{=html}
`<br/>`{=html}
`<img src="https://img.shields.io/badge/Streamlit-Interactive%20UI-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>`{=html}
`<img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas"/>`{=html}
`<img src="https://img.shields.io/badge/OpenRouter-LLM%20Routing-6B4EFF?style=flat-square" alt="OpenRouter"/>`{=html}
`<img src="https://img.shields.io/badge/IBM%20Bob-AI%20Coding%20Assistant-1261FE?style=flat-square&logo=ibm&logoColor=white" alt="IBM Bob"/>`{=html}
:::

  -----------------------------------------------------------------------
  Layer                   Technology              Purpose
  ----------------------- ----------------------- -----------------------
  UI framework            Streamlit               Interactive web
                                                  application

  Data processing         pandas                  CSV loading, feature
                                                  engineering, and
                                                  analysis

  LLM client              OpenAI-compatible       Sends prompts to the
                          Python SDK              configured model
                                                  endpoint

  LLM routing             OpenRouter              Routes requests to
                                                  `openai/gpt-4o-mini`

  Persistence             SQLite / `sqlite3`      Stores generated email
                                                  history

  Environment             python-dotenv           Loads local environment
  configuration                                   variables

  AI coding assistant     IBM Bob                 Supported analysis,
                                                  implementation,
                                                  testing, and
                                                  documentation
  -----------------------------------------------------------------------

## 📂 Project Structure

``` text
AI_Email_Campaign_Agent/
├── app.py                  # Streamlit UI and campaign workflow
├── gemini.py               # OpenRouter LLM wrapper
├── database.py             # SQLite storage and history functions
├── requirements.txt        # Python dependencies
├── marketing_campaign.csv  # Sample customer dataset
├── history.db              # Local database, created at runtime
├── main.ipynb              # Exploratory data analysis
├── IBM_BOB_USAGE.md        # IBM Bob contribution log
└── .env                    # Local API key; never commit this file
```

## ⚙️ Run Locally

### 1. Clone the repository

``` bash
git clone https://github.com/sarishadeel206/AI_Email_Campaign_Agent.git
cd AI_Email_Campaign_Agent
```

### 2. Create and activate a virtual environment

**Windows PowerShell**

``` powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux**

``` bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

Dependencies:

``` text
streamlit>=1.30.0
pandas>=2.0.0
openai>=1.0.0
python-dotenv>=1.0.0
```

### 4. Configure the API key

Create a `.env` file in the project root:

``` env
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

Keep the key private. Never commit `.env` or real API credentials to
GitHub.

### 5. Run the application

``` bash
streamlit run app.py
```

Open the local Streamlit URL shown in the terminal, usually
`http://localhost:8501`.

## 🧑‍💻 How to Use

1.  Upload `marketing_campaign.csv` or a compatible customer CSV.
2.  In **Campaign Generator**, optionally filter by segment.
3.  Select a customer and review their profile.
4.  Choose **Professional**, **Friendly**, or **Urgent** tone.
5.  Click **Generate Email**.
6.  Review the subject and body, then download the draft if needed.
7.  Use **Analytics** to explore customer patterns.
8.  Use **History** to review saved drafts or export the records as CSV.

## 🤖 IBM Bob: Development Contribution

IBM Bob Agent Mode was used as the primary AI coding assistant during
development.

-   **Analysis:** Examined the notebook and dataset to understand data
    structure and segmentation logic.
-   **Planning:** Helped shape the three-module design and database
    approach.
-   **Implementation:** Assisted in creating `app.py`, `gemini.py`,
    `database.py`, and `requirements.txt`.
-   **Testing:** Supported validation of CSV loading, segmentation,
    database operations, LLM output parsing, and error handling.
-   **Documentation:** Helped prepare the project contribution log.

Read more in
[`IBM_BOB_USAGE.md`](https://github.com/sarishadeel206/AI_Email_Campaign_Agent/blob/main/IBM_BOB_USAGE.md).

## ✅ Testing & Validation

The project documentation records checks for:

-   Loading the provided tab-separated dataset (2,240 rows and 29
    columns).
-   Computing `Age`, `Total_Purchases`, `Total_Spent`, `Customer_Value`,
    and `Segment`.
-   Initializing SQLite with fresh and existing databases.
-   Saving and retrieving records through SQLite.
-   Parsing `SUBJECT:` and `BODY:` from representative LLM responses.
-   Producing TXT and CSV downloads.
-   Handling empty segments, missing columns, API failures, and empty
    history.

## 🔭 Future Roadmap

-   **Batch generation** with progress tracking.
-   **Reusable email templates** for recurring campaigns.
-   **A/B subject line variants** for split testing.
-   **Multi-model selection** across supported OpenRouter models.
-   **Scheduled campaigns** and approval workflows.
-   **Email delivery integration** with providers such as SendGrid,
    Mailgun, or AWS SES.
-   **Authentication** for shared deployments.
-   **Cloud deployment** using Docker and a hosting platform.

## 🔐 Security Notes

-   Store API credentials in `.env`.
-   Add `.env`, `.venv/`, `history.db`, `__pycache__/`, and `*.pyc` to
    `.gitignore`.
-   Do not upload customer data or secrets without permission.
-   Review generated email content before using it in a real campaign.

## 📄 License

This project was developed as a hackathon submission. See the repository
for license details.

------------------------------------------------------------------------

::: {align="center"}
**Built with Python, customer data, and AI-assisted development.**

`<sub>`{=html}AI Email Campaign Automation Agent · Team NextGen
AI`</sub>`{=html}

`<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00D4FF,50:0F6CBD,100:071A2F&height=100&section=footer" width="100%" alt="Project footer"/>`{=html}
:::
