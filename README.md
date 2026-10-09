# SupportAI

SupportAI is a local-first customer support assistant built with FastAPI, React, ChromaDB, and Ollama.

## Quick start

1. Python 3.12.10
2. Node.js 20+
3. Ollama installed and running with `qwen2.5:3b`
4. Install backend dependencies:
   `cd backend && python -m venv .venv && .\.venv\Scripts\Activate.ps1 && pip install -r requirements.txt`
5. Install frontend dependencies:
   `cd frontend && npm install`
6. Start backend: `cd backend && uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`
7. Start frontend: `cd frontend && npm run dev -- --host 0.0.0.0 --port 5173`

## Architecture summary

- React dashboard for chat, documents, support tickets, analytics, and settings.
- FastAPI app hosts APIs and orchestrates ingestion, retrieval, and LLM calls.
- Chroma stores vector embeddings and metadata for support documents.
- SQLite stores app data and metadata.
- Ollama provides local LLM inference, defaulting to `qwen2.5:3b`.

## Main folders

- `backend/app/` — FastAPI app and domain services
- `backend/tests/` — automated tests
- `frontend/src/` — React + TypeScript frontend
- `data/` — uploads and local Chroma persistence
