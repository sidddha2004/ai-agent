📌 Project Overview

This project is a secure AI agent framework built with Django and LangGraph that allows large language models to safely interact with user data, internal application logic, and external APIs. Agents can answer natural-language queries by executing approved Python tools, querying Django ORM models directly, and integrating third-party REST services, without requiring vector embeddings unless explicitly needed.

The system enforces role-based access control (RBAC) using Permit to ensure that every action—such as create, read, update, search, share, or delete—is strictly permission-controlled. It supports multi-agent orchestration, including a Supervisor Agent that manages specialized sub-agents, and is LLM-agnostic, enabling easy model upgrades. The result is a controlled, auditable, and production-ready AI agent architecture designed for real-world Django applications.

⚡ Quick Start
1️⃣ Clone the Repository
git clone https://github.com/sidddha2004/ai-agent.git
cd ai-agent

2️⃣ Create & Activate Virtual Environment
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Configure Environment Variables

Set the following variables in:

src/cfehome/settings.py


Values are loaded using python-decouple.

Required Environment Variables
OPENAI_API_KEY=your_openai_api_key
TMDB_API_KEY=your_tmdb_api_key
PERMIT_API_KEY=your_permit_api_key
PERMIT_PDP_URL=https://cloudpdp.api.permit.io

5️⃣ Run Database Migrations
python manage.py makemigrations
python manage.py migrate

6️⃣ Create Admin User
python manage.py createsuperuser

7️⃣ Start the Server
python manage.py runserver


Visit the Django Admin panel:
👉 http://127.0.0.1:8000/admin

8️⃣ Start Chatting with Your Agent

Log in as admin or user

Assign roles & permissions

Query your data using natural language:

“What are my recent documents?”
“Summarize user activity this week” 