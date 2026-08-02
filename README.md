# LangChain Multi-Agent Research System

A multi-agent research system built with LangChain that searches for information, extracts relevant content, writes structured reports, and evaluates report quality

Research automation. Multi-agent orchestration. Report generation.

---

## Features

- Multi-agent architecture for searching, reading, writing, and critiquing
- Web research backed by Tavily search
- Content extraction with multiple fallback strategies
- Structured research report generation
- Built-in review and scoring step for report quality
- Streamlit user interface for interactive use
- End-to-end pipeline orchestration

---

## Architecture

```text
Streamlit UI (app.py)
		-> Research pipeline
				-> Search agent
				-> Reader agent
				-> Writer chain
				-> Critic chain
				-> Final report
```

### Agent responsibilities

- Search agent: finds relevant information on the web using Tavily
- Reader agent: extracts clean content from selected URLs
- Writer chain: produces a structured research report
- Critic chain: evaluates the report and suggests improvements

---

## Technologies Used

| Package            | Purpose                                      |
|--------------------|----------------------------------------------|
| LangChain          | Multi-agent orchestration and chain management |
| GENAI gemini-3.1-flash-lite | Language model for agents and chains         |
| Streamlit          | Interactive web UI                          |
| Tavily API         | Web search and retrieval                     |
| BeautifulSoup4     | HTML parsing and extraction                  |
| Trafilatura        | Web content extraction                       |
| Readability-lxml   | Article extraction                           |
| python-dotenv      | Environment variable loading                 |
| Rich               | Terminal output formatting    

---

## Prerequisites

- Python 3.11 or higher
- GENAI API key (Or any other provider)
- Tavily API key
- uv installed locally

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/ahra3/LangChain-Multi-Agent-Research-System.git
cd LangChain-Multi-Agent-Research-System
```

### 2. Create and activate a virtual environment with uv

```bash
uv venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS and Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
uv pip install .

```
### 4. Configure environment variables

Create a `.env` file in the project root:

```bash
GOOGLE_API_KEY=your_genai_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

---

## Usage

### Run the Streamlit app

```bash
streamlit run app.py
```

Open `http://localhost:8501` in your browser.

### Run as a script

```bash
python main.py
```

Update the `topic` value in `main.py` to research a different subject.

---

## Project Structure

```text
app.py
main.py
src/
	agents/
	pipelines/
	tools/
LangChainTutorial/
```

---

## Notes

- The system is designed for iterative research workflows.
- Report quality depends on the availability and reliability of source content.
- Search and extraction behavior may vary based on the target topic and source availability.
