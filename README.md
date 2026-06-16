# YouTube Video Search with Apify (n8n Workflow)

## Step 1. Defining the Problem Statement
Content creators, researchers, marketers, and learners struggle with manually searching YouTube and collecting relevant video URLs, which causes wasted time, inconsistent research workflows, and difficulty scaling content discovery.

- Who: Content creators, researchers, marketers, students, and AI enthusiasts
- Specific Pain: Manually searching YouTube and collecting video URLs
- Real Impact: Wasted time and inconsistent research workflows

---

## Step 2. Building a User Persona

#### Goals
- Discover relevant YouTube videos quickly
- Build research datasets
- Automate repetitive search tasks

#### Pain Points
- Manual searching
- Copy-pasting URLs
- Organizing results

#### Behaviors
- Frequent keyword searches
- Spreadsheet-based tracking
- Research-heavy workflows

---

## Step 3. Problem → Feature List

| Pain Point | Feature | User Value |
|------------|----------|------------|
| Manual YouTube searching | Keyword search form | Faster discovery |
| Collecting URLs manually | Apify automation | Saves time |
| Organizing results | Google Sheets storage | Structured data |
| Processing multiple videos | Split videos node | Scalability |

---

## Step 4. MVP vs Extended Scope

### MVP Features
- n8n Form
- Apify Request
- Wait Node
- Fetch Apify Records
- Extract URLs
- Split Videos
- Save to Google Sheets

### Extended Features
- Transcript extraction
- AI summaries
- Telegram alerts
- Channel analytics
- Duplicate detection

---

## Step 5. Writing a Proper PRD

### ① Problem Statement
Automate YouTube keyword searches and URL collection.

### ② User Persona
Researchers, creators, marketers, and learners.

### ③ Goals & Success Metrics
- Successful searches
- URL extraction
- Google Sheets storage

### ④ MVP Feature List
- Keyword form
- Apify integration
- URL extraction
- Google Sheets output

### ⑤ Extended Scope
- Transcripts
- AI summaries
- Notifications

### ⑥ Out of Scope
- Video downloading
- Publishing videos

### ⑦ Assumptions & Risks
- Apify availability
- API limits
- Dataset retrieval delays

---

## Step 6. Execution Planning

### Foundation First
#### n8n Form

[Input-form](docs/images/Input-form.png)

#### Apify Actor

[Apify-Actor](https://console.apify.com/actors/BuhSTDI7Mgd6NITMb/info/readme?build=latest)
Search YouTube videos using a keyword and return video URLs, video IDs, and metadata for downstream AI workflows. Designed for n8n integrations, content research, transcript generation, translation pipelines, and YouTube automation projects.

### Google Sheets

[Sheet DB](docs/images/Sheet-DB.png)

| Column | Purpose |
|----------|----------|
| Timestamp | Execution Time |
| Source_URL | Video URL |
| Telegram ID | Future Use |
| Current Stage | Processing Status |
| Platform | YouTube |

### Workflow Architecture - Happy Path Second

User Form
↓
Apify Request
↓
Wait 20 Seconds
↓
Fetch Apify Records
↓
IF Status = SUCCEEDED
↓
Extract Records
↓
Split Videos
↓
Google Sheets

@[n8n-Workflow](docs/images/Workflow.png)

### Test & Learn Third

Test Keywords:
- RAG
- AI Agents
- Machine Learning
- n8n Automation

---

# Business Value

- Automates YouTube research
- Saves manual effort
- Creates reusable datasets
- Supports AI pipelines

---

# Tech Stack

- n8n
- Apify
- Google Sheets
- YouTube Search
- HTTP Requests

---

# Outcome

Automated keyword-based YouTube search workflow that extracts video URLs and stores them in Google Sheets.
