# WeatherAI Architecture Overview

## Architecture overview
- **Frontend (Streamlit)**: `app.py` hosts the user interface and handles user input.
- **Backend (FastAPI)**: `api.py` exposes REST endpoints for forecasts and AI explanations.
- **LLM service (Gemini)**: `llm_service.py` wraps Gemini calls and isolates prompt logic.
- **Analytics**: `analytics.py` handles data cleaning and visualization with Pandas/NumPy/Matplotlib.
- **Tests**: `tests/` contains unit tests for services and analytics functions.

## Data flow (high level)
1. User submits a location or date range in Streamlit.
2. Streamlit calls the FastAPI endpoint.
3. FastAPI uses the Weather API key to fetch data and passes results to analytics.
4. FastAPI calls the Gemini service for explanations or summaries.
5. FastAPI returns structured results to Streamlit for display.

## Environment variables
Create a local `.env` file based on `.env.example` and add your API keys.

## Folder structure
```
WeatherAIPythonEksamen/
├── app.py
├── api.py
├── llm_service.py
├── analytics.py
├── tests/
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── .env.example
```
