```markdown
# ElectroMate — AI Voice Assistant for Electronics Store

**Tagline:** Your in-store AI expert for electronics.

---

## Overview
ElectroMate is a voice-enabled AI assistant designed for electronics stores. It answers user queries by retrieving relevant product knowledge from a vector database and delivering real-time, human-like spoken responses.

The system uses a Retrieval-Augmented Generation (RAG) pipeline to ensure accurate, context-aware answers based on your custom data.

---

## Features
- Voice-based responses using ElevenLabs  
- Context-aware answers via RAG  
- Supabase vector database integration  
- Real-time query handling via webhook  
- Modular workflow built on n8n  
- Custom knowledge base ingestion  

---

## Tech Stack
- n8n (workflow orchestration)  
- Supabase (vector database)  
- ElevenLabs (text-to-speech)  
- OpenRouter (LLM access)  
- Google Gemini (embeddings)  

---

## Architecture
```

User → Webhook → RAG Orchestrator (n8n)
↓
Supabase Vector Search
↓
LLM Response
↓
ElevenLabs (Voice)
↓
API Response

```

---

## How It Works
1. User sends a query via webhook  
2. Query is processed by the n8n workflow  
3. Relevant data is retrieved from Supabase  
4. LLM generates a context-aware answer  
5. Answer is converted to speech using ElevenLabs  
6. Voice response is returned to the user  

---

## Setup Instructions

### 1. Import Workflows
- Import `voice-agent.json` into n8n  
- (Optional) Import ingestion workflow  

### 2. Configure Credentials
Add the following API keys in n8n:
- OpenRouter API key  
- Supabase URL + API key  
- ElevenLabs API key  
- Google Gemini API key  

### 3. Prepare Database
- Set up Supabase project  
- Enable vector storage  
- Run ingestion workflow to populate data  

### 4. Run the System
- Activate workflow  
- Trigger webhook endpoint  
- Start querying  

---

## Example Use Cases
- Customer support assistant in electronics stores  
- Product recommendation system  
- Internal staff training assistant  
- Knowledge base voice interface  

---

## Project Structure
```

electromate-ai-assistant/
│
├── workflows/
│   ├── voice-agent.json
│   └── ingestion.json
│
├── docs/
│   └── setup.md
│
├── demo/
│   └── demo.mp4
│
└── README.md

```

---

## Important Notes
- API credentials are not included  
- Users must configure their own keys  
- Ensure Supabase vector table is properly set up  

---

## Future Improvements
- Streaming voice responses  
- Multi-language support  
- Frontend interface (web/mobile)  
- User authentication & memory  
- Analytics dashboard  

---

## Author
Developed as a portfolio project demonstrating practical AI system design using real-world tools and workflows.
```
