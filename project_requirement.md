# Modular Resume and Job Analysis Platform

## Project Requirement Document

### Project Title
Modular Resume and Job Analysis Platform

### Architecture
Agent-Orchestrated with CrewAI and MCP (Modular Control Points) Servers

## Objective
To build a full-featured, modular, AI-powered resume and job analysis platform using CrewAI for orchestration and MCP servers for tasks like scraping, NLP processing, validation, scoring, and reporting. The platform helps job seekers tailor resumes in real-time, generate ATS-optimized resumes, compare multiple jobs, and receive actionable feedback backed by AI-driven analysis.

## Detailed Requirements

### 1. User Interface (Frontend)
- Built with React
- Features:
  - Resume Upload Panel (PDF, DOCX, HTML)
  - Job URL/Description Input (with integrated scraper)
  - Real-time Resume Editor with AI Feedback Suggestions
  - Bulk Job Comparison Tool for comparing resume compatibility across multiple jobs
  - Configuration Panel:
    - Target role
    - Location preferences
    - Industry preferences
  - Feedback Viewer with Visualizations
  - ATS Compatibility Checker with pass/fail indicators
  - Company Culture Fit Analysis using public company data or embeddings
  - Report Download Panel (PDF)
  - Skill Recommendation Panel with upskilling links

### 2. Resume Processing Flow (MCP-enabled)
- Supports PDF, DOCX, HTML
- MCP agents:
  - MCP-PDF-free, MCP-DOC-free, MCP-HTML-free for parsing
  - MCP-NLP-huggingface for semantic extraction
  - MCP-STAT-newton for keyword statistics
  - Real-time feedback from parsing agents shown live on the editor
- Processed data stored in Chroma or Pinecone (vector DBs)

### 3. Job Description Analysis (with MCP Scrapers)
- Scrapes LinkedIn, Naukri, Indeed (via MCP-WEB-* scrapers)
- Uses MCP-PROXY-free for anti-bot handling
- Converts scraped job descriptions to structured format
- Extracts:
  - Keywords
  - Responsibilities
  - Requirements
  - Role summary
  - Salary data (if available)

### 4. Validation Flow (MCP-driven)
- Schema validation using dedicated agents
- Validation of:
  - ATS compliance
  - Formatting consistency
  - Completeness (e.g., missing dates, incomplete sections)

### 5. Scoring Engine Flow (Agent-based and MCP-driven)
- Compares resumes with jobs on:
  - Skill Match Percentage
  - Keyword Coverage
  - Experience Relevance
  - ATS Compatibility
- MCP modules:
  - MCP-TEXT-free
  - MCP-NLP-huggingface
  - MCP-STAT-newton
- Outputs matching scores with visual breakdowns

### 6. Feedback System
- Real-time Suggestions While Editing
- Includes:
  - Gap Analysis
  - Suggested improvements in content, keywords, sections
  - Formatting/template recommendations via MCP-PDF-free
  - Skill Recommender linked to external upskilling platforms

### 7. Bulk Job Comparison System
- Select multiple job URLs
- Run parallel analysis across all selected jobs
- Shows a comparison matrix of scores for each job-resume match
- Prioritizes applications based on best-fit match

### 8. ATS Optimization Checker
- Pass/Fail style scoring for ATS systems
- Feedback on:
  - Overuse of graphics
  - Non-readable fonts
  - Tables, images breaking parsing
- Recommendations to make resumes ATS-safe

### 9. Company Culture Fit Analysis
- Uses public company data (scraped and embedded) to suggest cultural fit
- Provides tips on aligning tone and content with specific company culture

### 10. Report Generation and Delivery
- PDF report generation (MCP-PDF-free) with visual charts (MCP-CHART-free)
- Reports include:
  - Matching summary
  - Feedback
  - Improvement recommendations
  - Skill recommendations with links to external resources
- Delivery:
  - Email with formatted body
  - Download link via UI

### 11. Data Persistence
- Results stored in SQLite (for local MVP) or PostgreSQL (scalable version)
- Logs handled by MCP-LOG-free

### 12. Backend Orchestration (CrewAI + MCP Architecture)
- CrewAI used to orchestrate all flows:
  - Resume Processing Flow
  - Job Analysis Flow
  - Validation Flow
  - Scoring Engine Flow
  - Feedback System Flow
  - Report Generation Flow
- MCP Controllers handle:
  - NLP tasks
  - File processing
  - Data validation
  - Visualization
  - Scraping
- Modular approach for horizontal scalability and plug-and-play MCP services

## Tech Stack Overview

| Area             | Technology                   |
| ---------------- | ---------------------------- |
| Frontend         | React                        |
| Backend          | Python (FastAPI / Flask)     |
| Agent System     | CrewAI                       |
| Task Control     | MCP Servers                  |
| Vector Database  | Pinecone / Chroma            |
| Database         | SQLite / PostgreSQL          |
| Scraping         | MCP-WEB-* + Proxy Handling   |
| NLP              | Huggingface, OpenAI (MCP)    |
| Visualization    | MCP-CHART-free + Chart.js    |
| PDF Reports      | PDFKit / MCP-PDF-free        |
| Logging          | MCP-LOG-free                 |

## Goal
Deliver a production-grade, modular, extensible resume intelligence platform capable of real-time feedback, batch analysis, ATS optimization, and skill recommendation, ready for integration with external services (LMS, job portals, ATS systems).
