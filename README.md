# brandora-ai-cofounder-engine

LLM-powered marketing workflow system for D2C brands

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

git clone https://github.com/Shekhar2298/brandora-ai-cofounder-engine
cd brandora-ai-cofounder-engine


Start services:

docker-compose up --build


Backend runs at:

http://localhost:8000/docs


Frontend dashboard:

http://localhost:3000
