# Modular Resume and Job Analysis Platform (ATS Checker) with FastAPI, CrewAI, FastMCP servers

![diagram-export-13-06-2025-12_03_15](https://github.com/user-attachments/assets/287f2856-d79f-4094-abc7-bbdb040d65fb)

A full-stack modular AI-driven platform for advanced resume parsing, job analysis, intelligent scoring, structured feedback, and reporting. Powered by FastAPI, CrewAI, and FastMCP with a modern React frontend.

## Features
- Resume parsing (PDF, DOCX, HTML)
- Job description scraping and analysis (LinkedIn, Naukri, Indeed)
- AI-based resume-to-job matching with advanced scoring
- Automated feedback and personalized improvement suggestions
- PDF report generation and email delivery
- Fully modular architecture using CrewAI and MCP-based agents
- Extensible for future AI task integrations

## Technology Stack
- **Backend**: FastAPI + CrewAI + FastMCP
- **Frontend**: React (Vite)
- **Database**: SQLite (default, replaceable)
- **Agents and Tasks**: CrewAI + MCP Controllers

---

## Backend Environment Setup (FastAPI + CrewAI + FastMCP)

### 1. Clone the Repository

```bash
git clone https://github.com/KaushalprajapatiKP/ATS-Checker-Resume-using-CrewAI-MCP
cd https://github.com/KaushalprajapatiKP/ATS-Checker-Resume-using-CrewAI-MCP/backend
```

### 2. Environment Creation (using uv)

```bash
uv venv
uv sync
uv lock
```

### 3. Environment Activation (using uv)

```bash
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows
```

### 4. Dependency Installation

```bash
uv pip install -r requirements.txt
```

### 5. Sync and Lock Environment

```bash
uv pip sync     # Ensures environment matches lock file
uv pip compile  # Generates requirements.lock.txt (if needed)
```

### 6. Run Backend Server

```bash
uvicorn app.main:app --reload
```

## Backend Environment Setup (Using pip)

### 1 Create Virtual Environment

```bash
python3 -m venv venv
```

### 2 Activate environment:

**macOS/Linux:**

```bash
source venv/bin/activate
```

**Windows:**

```powershell
venv\Scripts\activate
```

### 3 Install Dependencies

```bash
pip install -r requirements.txt
```

Or (if using `pyproject.toml`):

```bash
pip install .
```


## Frontend Environment Setup (React)

### 1. Initialize React Project in Root folder

If not initialized:

```bash
npm create vite@latest frontend -- --template react
```

### 3. Install Dependencies

```bash
cd frontend
npm install
```

### 4. Run Frontend

```bash
npm run dev
```

### 5. Environment Activation for Development

```bash
# Backend
source ../backend/.venv/bin/activate  # macOS/Linux
.venv\Scripts\Activate                # Windows


# Frontend (already active with npm)
```

---




