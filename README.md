# Autonomous Multi-Agent AI Newsroom & Newsletter Engine

An end-to-end AI-powered content automation pipeline built with n8n, Supabase, OpenRouter, Tavily, and Gmail.

The system automatically monitors RSS feeds for the latest AI and technology news, prevents duplicate processing using a PostgreSQL database, enriches articles with external web research, generates newsletter-ready content through a multi-stage AI workflow, and delivers curated newsletters via email.

---

## Project Overview

This workflow transforms raw news articles into fully generated newsletter content without manual intervention.

The pipeline:

1. Collects the latest AI news from RSS feeds.
2. Checks a Supabase (PostgreSQL) database to prevent duplicate processing.
3. Uses Tavily Search to gather additional context and recent information.
4. Runs the content through a specialized AI agent pipeline:
   - News Analyzer
   - Table of Contents Generator
   - Article Writer
   - Fact Checker
   - Content Editor
   - Title Generator
   - Image Prompt Generator
5. Stores processed records in Supabase.
6. Automatically delivers the generated newsletter through Gmail.

---

## System Architecture

```text
Schedule Trigger
        │
        ▼
RSS Feed Reader
        │
        ▼
Supabase Duplicate Check
        │
        ▼
Validation Layer
        │
        ▼
AI News Analyzer
        │
        ▼
Tavily Research Enrichment
        │
        ▼
TOC Generator
        │
        ▼
Body Writer
        │
        ▼
Fact Checker
        │
        ▼
Content Editor
        │
        ▼
Title Generator
        │
        ▼
Image Prompt Generator
        │
        ▼
Aggregation Layer
        │
        ▼
Supabase Storage
        │
        ▼
Gmail Newsletter Delivery
```

---

## Key Features

### Automated News Monitoring

Fetches the latest AI and technology articles from RSS feeds on a scheduled basis.

### Duplicate Detection (Idempotency)

Uses Supabase (PostgreSQL) to ensure previously processed articles are skipped automatically.

### AI-Powered Research

Enhances incoming articles with additional context using Tavily Search.

### Multi-Agent Content Pipeline

Specialized AI agents perform different responsibilities:

- News Analysis
- TOC Creation
- Long-form Article Writing
- Fact Checking
- Content Editing
- Title Generation
- Image Prompt Creation

### Automated Newsletter Delivery

Generates and emails a formatted newsletter without human intervention.

---

## Technology Stack

| Category | Technology |
|-----------|------------|
| Workflow Orchestration | n8n |
| Database | Supabase (PostgreSQL) |
| LLM Provider | OpenRouter |
| Model | GPT-4o Mini |
| Research Layer | Tavily Search API |
| Email Service | Gmail API |
| Content Storage | Supabase |
| Automation | Scheduled Cron Workflow |

---

## Database Design

### Table: `processed_article`

| Column | Description |
|----------|------------|
| title | Original article title |
| link | Article URL |
| summary | AI-generated summary |
| created_at | Processing timestamp |

The table acts as a persistent record store and enables duplicate prevention.

---

## AI Agent Pipeline

### 1. AI News Analyzer

Extracts:
- News title
- Key summary points
- Research query

### 2. TOC Generator

Creates a structured newsletter outline.

### 3. Body Writer

Produces a detailed article based on the generated outline.

### 4. Fact Checker

Reviews and improves factual consistency.

### 5. Content Editor

Refines readability, formatting, and structure.

### 6. Title Generator

Generates multiple newsletter title options.

### 7. Image Prompt Generator

Creates AI image generation prompts for visual assets.

---

## Sample Output

The system generates:

- News Summary
- Full Newsletter Article
- Newsletter Titles
- AI Image Prompt
- Email Digest

---

## Installation

### Prerequisites

- Docker
- n8n
- Supabase Account
- OpenRouter API Key
- Tavily API Key
- Gmail OAuth Credentials

---

### Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/autonomous-ai-newsroom.git
cd autonomous-ai-newsroom
```

---

### Import Workflow

1. Open n8n.
2. Import the workflow JSON file.
3. Configure credentials:
   - OpenRouter
   - Tavily
   - Supabase
   - Gmail
4. Activate the workflow.

---

## Future Improvements

- AI image generation and storage
- Newsletter analytics dashboard
- Click/open rate tracking
- Multi-feed ingestion
- Vector database integration
- Retrieval-Augmented Generation (RAG)
- Human approval workflow

---

## Resume Description

Built an AI-powered automated newsroom pipeline using n8n, Supabase, OpenRouter, Tavily, and Gmail that collects news from RSS feeds, prevents duplicate processing, enriches content through web research, generates newsletter-ready articles using a multi-agent AI workflow, and automatically delivers curated newsletters via email.

---

## Author

Bhavya Joshi

B.Tech CSE, IIIT Kota
