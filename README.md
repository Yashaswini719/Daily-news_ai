Daily News AI

Daily News AI is an AI-powered news aggregation system that collects, processes, and delivers concise news summaries from multiple sources using modern data pipelines and large language models.

 Overview

Daily News AI automates the end-to-end workflow of news aggregation:

Collects content from multiple online sources
Processes and filters relevant information
Generates AI-powered summaries
Stores structured data in a database
Delivers curated news digests


Key Features
Multi-source aggregation – Supports web scraping, RSS feeds, and video transcripts
AI summarization – Generates concise summaries using LLMs
Automated pipeline – End-to-end processing with minimal manual intervention
Database integration – Stores structured news data for retrieval and analysis
Email-ready digests – Prepares content for automated delivery
Scalable architecture – Designed for real-world production workflows


Architecture

The system follows a modular pipeline:

Data Ingestion – Fetch news from multiple sources
Processing Layer – Clean and structure content
AI Layer – Generate summaries using OpenAI
Storage Layer – Persist data in PostgreSQL
Delivery Layer – Prepare and send digest outputs
🛠️ Tech Stack
Language: Python
AI: OpenAI API
Database: PostgreSQL
ORM: SQLAlchemy
Scraping: BeautifulSoup, Feedparser
Infrastructure: Docker
Dependency Management: uv


Project Structure
daily-news-ai/
│
├── app/
│   ├── scrapers/        # Data collection modules
│   ├── agent/           # AI summarization logic
│   ├── database/        # Database models & connection
│   ├── services/        # Core business logic
│   └── daily_runner.py  # Pipeline orchestration
│
├── docker/              # Database setup
├── main.py              # Entry point
├── .env                 # Environment variables
├── pyproject.toml       # Dependencies



⚙️ Setup
1. Install dependencies
uv sync
2. Configure environment variables

Create a .env file:

OPENAI_API_KEY=your_api_key
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB=daily_news_ai
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
3. Start database
docker compose -f docker/docker-compose.yml up -d
4. Run the pipeline
uv run main.py

Output
Structured news entries stored in PostgreSQL
AI-generated summaries
Ready-to-send daily news digest

Notes
Ensure your OpenAI API key is valid and billing is enabled
PostgreSQL must be running before executing the pipeline
