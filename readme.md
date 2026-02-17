A secure, production-ready AI agent framework that lets LLMs safely interact with Django user data, internal logic, and external APIs, with strict role-based access control.

📌 Overview

This project enables large language models to:

Query Django ORM data directly

Execute approved Python tools

Integrate third-party REST APIs

Operate under strict RBAC policies using Permit

It supports multi-agent orchestration, including a Supervisor Agent, and is LLM-agnostic, allowing easy model upgrades without changing core logic.

⚡ Quick Start
1. Clone the Repository
git clone https://github.com/sidddha2004/ai-agent.git
cd ai-agent

2. Create & Activate Virtual Environment
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

3. Install Dependencies
pip install -r requirements.txt

4. Environment Configuration

Add the following variables in src/cfehome/settings.py
(loaded using python-decouple):

OPENAI_API_KEY=your_openai_api_key
TMDB_API_KEY=your_tmdb_api_key
PERMIT_API_KEY=your_permit_api_key
PERMIT_PDP_URL=https://cloudpdp.api.permit.io

5. Run Migrations
python manage.py makemigrations
python manage.py migrate

6. Create Admin User
python manage.py createsuperuser

7. Start the Server
python manage.py runserver


Open:
👉 http://127.0.0.1:8000/admin

8. Use the AI Agent

Log in as admin or user

Assign roles & permissions

Ask natural-language queries:

What are my recent documents?

Summarize user activity this week

🧱 Tech Stack

Backend: Django

Agents: LangGraph

Auth & Permissions: Django Auth + Permit

LLMs: Pluggable (OpenAI / others)

Data: Django ORM (optional vector DB)
