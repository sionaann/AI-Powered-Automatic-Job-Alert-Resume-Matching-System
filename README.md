# 🚀 AI-Powered Automatic Job Alert & Resume Matching System

An intelligent job search automation workflow built with n8n that automatically finds relevant LinkedIn jobs, evaluates them against your resume using Google Gemini AI, generates personalized cover letters, stores results in Google Sheets, and sends Telegram notifications for high-match opportunities.

---

## 📌 Features

- Automated daily job search
- Resume extraction from PDF
- Dynamic LinkedIn search filters
- AI-powered resume-job matching
- Match score generation
- Personalized cover letter creation
- Google Sheets integration for tracking
- Telegram alerts for top opportunities
- Duplicate job prevention
- Customizable search preferences

---

## 🏗 Workflow Architecture

```text
Schedule Trigger
      ↓
Download Resume (Google Drive)
      ↓
Extract Resume Text
      ↓
Load Search Filters (Google Sheets)
      ↓
Generate LinkedIn Search URL
      ↓
Fetch Job Listings
      ↓
Extract Job Details
      ↓
AI Resume Matching (Google Gemini)
      ↓
Generate Match Score + Cover Letter
      ↓
Store Results in Google Sheets
      ↓
Send Telegram Alert (High Match Jobs)
```

---

## ⚙️ How It Works

### 1. Resume Processing
The workflow downloads your resume from Google Drive and extracts text from the PDF for analysis.

### 2. Job Search Configuration
Search preferences are managed through Google Sheets, including:

- Keywords
- Location
- Experience Level
- Remote/Hybrid/On-site
- Job Type
- Easy Apply Filter

### 3. Job Collection
The workflow automatically searches LinkedIn for jobs posted within the last 24 hours and extracts:

- Job Title
- Company
- Location
- Description
- Application Link

### 4. AI Analysis
Google Gemini compares your resume with each job description and generates:

- Match Score (0–100)
- Tailored Cover Letter

### 5. Job Tracking
Results are automatically stored in Google Sheets.

### 6. Instant Alerts
Jobs above the configured score threshold trigger a Telegram notification containing:

- Job Title
- Company Name
- Application Link

---

## 📊 Google Sheets Structure

### Filter Sheet

| Column | Description |
|----------|------------|
| Keyword | Job title or skill |
| Location | Preferred location |
| Experience Level | Internship, Entry, Associate, Mid-Senior |
| Remote | Remote, Hybrid, On-site |
| Job Type | Full-time, Part-time, Contract, Internship |
| Easy Apply | TRUE/FALSE |

### Results Sheet

| Column | Description |
|----------|------------|
| Title | Job title |
| Company | Company name |
| Location | Job location |
| Link | Application URL |
| Description | Job description |
| Score | AI match score |
| Cover Letter | AI-generated cover letter |

---

## 🛠 Tech Stack

- n8n
- Google Gemini AI
- Google Drive API
- Google Sheets API
- Telegram Bot API
- LinkedIn Job Search
- JavaScript

---

## 📦 Requirements

Before running the workflow, configure:

### Google Drive
- Resume PDF storage

### Google Sheets
- Search filter sheet
- Results sheet

### Google Gemini API
- API key for AI scoring and cover letter generation

### Telegram Bot
- Bot token
- Chat ID

### n8n
- Self-hosted or cloud instance

---

## 🚀 Setup

### Step 1
Import the workflow into n8n.

### Step 2
Create a Google Sheet with:

- Filter tab
- Results tab

### Step 3
Upload your resume PDF to Google Drive.

### Step 4
Configure credentials:

- Google Drive
- Google Sheets
- Google Gemini
- Telegram

### Step 5
Update:
- Resume file URL
- Spreadsheet IDs
- Telegram Chat ID

### Step 6
Activate the workflow.

---

## 📈 Example Output

### Telegram Notification

```text
Title: AI Engineer

Company: Example Inc

Apply:
https://www.linkedin.com/jobs/view/123456789
```

### AI Response

```json
{
  "score": 87,
  "coverLetter": "Generated cover letter tailored to the role..."
}
```

---

## 🎯 Benefits

- Saves hours of manual job searching
- Prioritizes the most relevant opportunities
- Generates application-ready cover letters
- Maintains a searchable job database
- Never misses newly posted jobs

---

## 🔮 Future Enhancements

- Indeed integration
- Wellfound integration
- Naukri integration
- ATS score optimization
- Automatic application submission
- Email notifications
- Job analytics dashboard
- Multi-resume support

---

## 🤝 Contributing

Contributions, feature requests, and improvements are welcome.

Feel free to fork the repository and submit a pull request.

---

## 📄 License

MIT License

---

## ⭐ Support

If you found this project useful, consider giving it a star on GitHub.

It helps others discover the project and motivates future improvements.
