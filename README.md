A powerful AI-powered research assistant built using LangChain, OpenAI GPT models, Tavily Search API, and Streamlit.

This project uses a multi-agent architecture where different AI agents collaborate to:

Search the web for information
Read and scrape websites
Generate detailed research reports
Critically review the generated report

The application provides a modern Streamlit interface for performing automated AI research workflows.

🚀 Features
✅ Multi-Agent Workflow

The system contains multiple AI agents working together:

Search Agent
Searches the internet using Tavily API
Finds recent and reliable information
Reader Agent
Scrapes website content
Extracts clean readable text from URLs
Writer Chain
Generates a professional research report
Structures output into Introduction, Findings, Conclusion, and Sources
Critic Chain
Reviews the report
Gives score, strengths, and improvements
🛠️ Tech Stack
Python
LangChain
OpenAI GPT-4o-mini
Tavily Search API
Streamlit
BeautifulSoup
Requests
dotenv
📂 Project Structure
Multi-agent-research-system-main/
│
├── app.py               # Streamlit frontend UI
├── agents.py            # AI agents and chains
├── pipeline.py          # Main research workflow pipeline
├── tools.py             # Search and scraping tools
├── requirements.txt     # Project dependencies
└── .gitignore
⚙️ Installation Guide
1️⃣ Clone the Repository
git clone https://github.com/your-username/multi-agent-research-system.git
cd multi-agent-research-system
2️⃣ Create Virtual Environment
Windows
python -m venv env
env\Scripts\activate
Mac/Linux
python3 -m venv env
source env/bin/activate
3️⃣ Install Dependencies
pip install -r requirements.txt
🔑 Environment Variables Setup

Create a .env file in the root directory.

Add the following keys:
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
▶️ Run the Application
Run Streamlit App
streamlit run app.py

After running the command, open the browser and visit:

http://localhost:8501
🧠 How the System Works
Step 1 — Search Agent

The Search Agent searches the internet for the given topic.

Example:

search_result = search_agent.invoke({
    "messages": [("user", f"Find recent information about: {topic}")]
})
Step 2 — Reader Agent

The Reader Agent selects useful URLs and scrapes the content.

reader_result = reader_agent.invoke({
    "messages": [("user", "Scrape the best URL")]
})
Step 3 — Writer Chain

The Writer Chain generates a detailed report.

Output structure:

Introduction
Key Findings
Conclusion
Sources
Step 4 — Critic Chain

The Critic reviews the report and provides:

Score
Strengths
Improvements
Final Verdict
📸 Example Workflow
User Input
Artificial Intelligence in Healthcare
System Output
1. Searches web resources
2. Scrapes relevant articles
3. Generates research report
4. Reviews and scores report
📦 Dependencies

Main dependencies used in this project:

langchain
langchain-openai
streamlit
openai
beautifulsoup4
requests
python-dotenv
tavily-python
🧪 Example Commands
Run Pipeline Directly
python pipeline.py
🔍 Important Files Explained
agents.py

Contains:

Search Agent
Reader Agent
Writer Chain
Critic Chain
tools.py

Contains custom tools:

web_search()

Uses Tavily API for web search.

scrape_url()

Scrapes and cleans website text.

pipeline.py

Controls the complete workflow:

Search → Scrape → Write → Critic Review
app.py

Provides the modern Streamlit user interface.

Features:

Beautiful dark theme UI
Interactive workflow visualization
Real-time processing
Report display
🎯 Future Improvements

Possible enhancements:

PDF report export
Multi-source scraping
Vector database integration
RAG architecture
Memory-enabled agents
Citation generation
Research history storage
Multi-model support
🐞 Common Errors & Fixes
1. Missing Tavily API Key

Error:

tavily.errors.MissingAPIKeyError

Solution:

Make sure .env file contains:

TAVILY_API_KEY=your_key
2. OpenAI Authentication Error

Solution:

OPENAI_API_KEY=your_key
3. Streamlit Not Found

Install streamlit:

pip install streamlit
📈 Learning Concepts Used

This project demonstrates:

AI Agents
LangChain Tools
Tool Calling
LLM Chains
Prompt Engineering
Web Scraping
Multi-Agent Systems
Research Automation
Streamlit UI Development
