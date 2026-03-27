# ElectroMate — AI Voice Assistant for Electronics Store

**Tagline:** Your in-store AI expert for electronics.

---

## Overview

ElectroMate is an AI-powered voice assistant designed for electronics stores. It answers user queries by retrieving relevant product knowledge from a vector database and delivering real-time, human-like spoken responses.

The system uses a Retrieval-Augmented Generation (RAG) pipeline to ensure accurate, context-aware answers based on custom data.

---

## Features

* Voice-based responses using ElevenLabs
* Context-aware answers via RAG
* Supabase vector database integration
* Real-time query handling via webhook
* Modular workflows built on n8n
* Custom knowledge base ingestion pipeline

---

## Tech Stack

* n8n (workflow orchestration)
* Supabase (vector database)
* ElevenLabs (text-to-speech)
* OpenRouter (LLM access)
* Google Gemini (embeddings)

---

## Architecture

### Data Flow (Ingestion)

Google Sheets → Data Processing → Embeddings (Gemini) → Supabase Vector Store

### Query Flow (Voice AI)

User → Webhook → RAG Orchestrator (n8n) → Supabase Vector Search → LLM Response → ElevenLabs (Voice) → API Response

---

## Workflows

### 1. Voice AI Agent

Handles user queries and returns voice responses.

* `workflows/voice-agent.json`

### 2. Data Ingestion Pipeline

Processes and stores knowledge into the vector database.

* Reads data from Google Sheets

* Cleans and formats content

* Generates embeddings using Gemini

* Stores vectors in Supabase

* `workflows/ingestion.json`

---

## How It Works

1. Data is ingested from Google Sheets into Supabase as embeddings
2. User sends a query via webhook
3. Relevant data is retrieved using vector similarity
4. LLM generates a context-aware response
5. Response is converted into speech using ElevenLabs
6. Final output is returned to the user

---

## Setup Instructions

### 1. Import Workflows

* Import `voice-agent.json` into n8n
* Import `ingestion.json` (for data setup)

### 2. Configure Credentials

Add the following credentials in n8n:

* OpenRouter API key
* Supabase URL and API key
* ElevenLabs API key
* Google Gemini API key

### 3. Prepare Database

* Create a Supabase project
* Enable vector support
* Run ingestion workflow to populate data

### 4. Run the System

* Activate the workflow
* Trigger the webhook endpoint
* Start querying

---

## Example

**Input:**
"What is the best laptop under ₹70,000?"

**Output:**
A context-aware answer generated using your data, delivered as natural voice.

---

## Project Structure

electromate-ai-assistant/
├── workflows/
│   ├── voice-agent.json
│   └── ingestion.json
├── architecture/
│   └── workflow.png
└── README.md

---

## Use Cases

* Electronics retail store assistant
* Product recommendation system
* Customer support automation
* Internal knowledge assistant

---

## Important Notes

* API credentials are not included
* Users must configure their own keys
* Ensure Supabase vector table is properly set up

---

## Future Improvements

* Streaming voice responses
* Multi-language support
* Frontend UI (web/mobile)
* User authentication and memory
* Analytics dashboard

---

## Author

Developed as a portfolio project demonstrating end-to-end AI system design using automation, RAG, and voice technologies.
