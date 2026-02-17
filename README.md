# brandora-ai-cofounder-engine

LLM-powered marketing workflow system for D2C brands

 GitHub Repo Structure
brandora-ai-cofounder-engine/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── config.py
│   │   ├── api/
│   │   │   ├── routes.py
│   │   │   ├── marketing.py
│   │   │   ├── products.py
│   │   │   └── health.py
│   │   │
│   │   ├── services/
│   │   │   ├── llm_client.py
│   │   │   ├── rag_engine.py
│   │   │   ├── prompt_templates.py
│   │   │   ├── evaluation.py
│   │   │   └── campaign_generator.py
│   │   │
│   │   ├── db/
│   │   │   ├── database.py
│   │   │   ├── models.py
│   │   │   └── vector_store.py
│   │   │
│   │   ├── workers/
│   │   │   ├── celery_worker.py
│   │   │   └── tasks.py
│   │   │
│   │   └── utils/
│   │       ├── logger.py
│   │       └── helpers.py
│   │
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── pages/
│   │   ├── index.tsx
│   │   ├── dashboard.tsx
│   │   └── campaigns.tsx
│   │
│   ├── components/
│   │   ├── CampaignCard.tsx
│   │   └── UploadProducts.tsx
│   │
│   ├── package.json
│   └── Dockerfile
│
├── infra/
│   ├── docker-compose.yml
│   ├── postgres-init.sql
│   └── azure-deploy-notes.md
│
├── docs/
│   ├── architecture.md
│   ├── tradeoffs.md
│   └── loom-script.md
│
├── .env.example
├── README.md
└── LICENSE


Brandora AI Co-Founder Engine

AI-powered marketing workflow system for D2C brands

Overview

This project is a backend-first AI system that simulates an “AI Co-Founder” for D2C brands by generating high-quality marketing campaigns using LLM + Retrieval-Augmented Generation (RAG).

It supports structured workflows across:

Product understanding

Campaign generation

Async execution

Evaluation + iteration

Designed for scalability, low-latency, and real-world deployment.

Key Features
LLM Campaign Generation

Generates ad copy, email sequences, and product positioning

Uses OpenAI/Gemini APIs with structured prompts

Retrieval-Augmented Generation (RAG)

Stores product knowledge in Postgres + pgvector

Retrieves relevant context before generation

Async Processing Pipeline

Campaign generation runs as background jobs

Powered by Celery + Redis queue

Production-Oriented Architecture

Modular service boundaries

Clean API layer

Dockerized for deployment

Tech Stack

Backend

FastAPI (Python)

PostgreSQL + pgvector

OpenAI API

Celery + Redis

Frontend

Next.js + React dashboard

Infra

Docker Compose

Azure deployment-ready structure

Architecture

High-level workflow:

Upload product catalog

Store embeddings in vector DB

User requests campaign generation

Async worker generates outputs

Results stored + displayed in dashboard

Key Tradeoffs

Latency vs Quality
Real-time preview uses fast prompts, deeper enrichment runs async.

Cost vs Context Size
Retrieval reduces token usage by injecting only relevant product info.

Modularity vs Speed
Separate services allow scaling independently.

Running Locally

Clone repo:

git clone https://github.com/yourname/brandora-ai-cofounder-engine
cd brandora-ai-cofounder-engine


Start services:

docker-compose up --build


Backend runs at:

http://localhost:8000/docs


Frontend dashboard:

http://localhost:3000
