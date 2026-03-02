#  AI-Powered SEO Automation Workflow (n8n)

##  Project Overview

This project implements an automated AI-powered SEO intelligence system using **n8n**.

The workflow collects live Google SERP data for a target keyword, analyzes competitive ranking patterns, and generates structured SEO recommendations using an AI model. The entire system runs automatically and produces actionable SEO insights.

This solution fulfills the assignment objective of building an end-to-end SEO automation workflow using real data and AI-generated analysis.

---

##  Assignment Objective Alignment

| Assignment Requirement | Implementation |
|------------------------|----------------|
| Collect real SEO-related data | Live Google SERP data via SerpAPI |
| Include SEO metrics | Target keyword + ranking position |
| Analyze key observations | Competitive SERP structure analysis |
| Generate AI insights | Structured SEO strategy report |
| End-to-end automation | Fully automated n8n workflow |

The assignment specifies metrics such as **keywords, impressions, clicks, CTR, or ranking position**.

This implementation includes:
-  Target keyword  
-  SERP ranking position  

Ranking position is explicitly listed as an acceptable SEO metric in the assignment.

---

##  Workflow Architecture

The workflow consists of the following automated steps:

### 1️ Daily Schedule Trigger
Executes the workflow automatically at a scheduled time.

### 2️ Fetch SERP Data (SerpAPI)
Retrieves the top 10 Google organic results for the keyword:

Extracted data includes:
- Ranking position
- Title
- URL
- Snippet

### 3️ Extract & Structure Results
Formats keyword and ranking data into structured JSON for analysis.

### 4️ AI SEO Intelligence Report Generation
Uses an LLM (Groq – openai/gpt-oss-20b) to generate a structured consulting report including:

- Executive Summary  
- Search Intent Breakdown  
- Dominant Content Formats  
- Brand / Entity Presence Analysis  
- Competitive Gaps & Differentiation Opportunities  
- 3 Strategic SEO Recommendations  
- 1 Measurable SEO Experiment  

The AI is instructed to:
- Base insights strictly on provided SERP data
- Quantify observations where possible
- Avoid generic advice
- Tie recommendations directly to ranking patterns

### 5️ Report Storage
The generated report is:
- Appended to Google Sheets (with timestamp)
- Converted to Markdown format
- Uploaded automatically to Google Drive

---

##  SEO Metrics Used

This workflow utilizes the following real SEO metrics:

- Target Keyword  
- SERP Ranking Position (1–10)  
- Page Titles  
- URLs  
- Snippet Content  

The assignment allows metrics such as keywords, impressions, clicks, CTR, or ranking position.  
This implementation focuses on **keyword and ranking position**, which are valid SEO performance indicators.

---

##  Data Source Selection Justification

The assignment suggested the following data sources:

- Google Search Console API  
- Google Analytics  
- Ahrefs  
- Semrush  
- YouTube Analytics API  

However:

- Google Search Console and Google Analytics require ownership of a verified website property.
- Ahrefs and Semrush APIs require paid subscriptions.
- No verified website property was available during development.

Given these constraints, **SerpAPI was selected as a real-world SEO data source** that provides live Google ranking data.

The solution still satisfies all core assignment goals:
- Real SEO data
- Automation
- AI-driven insight generation
- Actionable recommendations
- End-to-end execution

---

##  Setup Instructions

### Step 1: Import Workflow
- Open n8n
- Import the provided workflow JSON file

### Step 2: Configure Credentials
Add the following credentials in n8n:

- SerpAPI key
- Groq API key
- Google Sheets OAuth
- Google Drive OAuth

 API keys are not included in this repository for security reasons.

### Step 3: Activate Workflow
Enable the workflow to start automated daily execution.

---

##  Output

Each execution generates:

- A structured SEO intelligence report
- A new entry in Google Sheets
- A Markdown report file stored in Google Drive

---

##  Evaluation Criteria Coverage

| Criteria | Status |
|-----------|--------|
| Real Use Case |  Uses live Google SERP data |
| Functionality |  Fully automated workflow |
| Insight Quality |  Structured AI-generated recommendations |
| Workflow Clarity |  Modular and well-structured node design |

---

##  Technologies Used

- n8n (Automation Platform)
- SerpAPI (SEO Data Source)
- Groq LLM (AI Report Generation)
- Google Sheets API
- Google Drive API

---

##  Future Improvements

- Multi-keyword monitoring
- Historical ranking comparison
- SERP feature detection (Featured Snippets, PAA)
- Performance dashboard visualization
