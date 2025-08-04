\# API Documentation



\## Base URL



Production: https://api.rag-system.com/v1

Development: http://localhost:8000/v1





\## Authentication

All API endpoints require authentication via JWT token:

```bash

Authorization: Bearer <your-jwt-token>

```



\## Core Endpoints



\### Document Management

\- `POST /documents/upload` - Upload document for processing

\- `GET /documents/{document\_id}` - Retrieve document metadata

\- `DELETE /documents/{document\_id}` - Remove document from system



\### Query \& Search

\- `POST /query` - Execute RAG query against document corpus

\- `GET /search` - Semantic search without LLM generation

\- `POST /batch-query` - Process multiple queries efficiently



\### System \& Monitoring

\- `GET /health` - System health check

\- `GET /metrics` - Performance metrics

\- `GET /status` - Current system status



\## Response Formats



\### Successful Query Response

```json

{

&nbsp; "query": "What is the revenue growth?",

&nbsp; "answer": "Based on the financial documents...",

&nbsp; "sources": \[

&nbsp;   {

&nbsp;     "document\_id": "doc\_123",

&nbsp;     "page": 15,

&nbsp;     "relevance\_score": 0.94

&nbsp;   }

&nbsp; ],

&nbsp; "confidence": 0.91,

&nbsp; "processing\_time": 1.8

}

```



\### Error Response

```json

{

&nbsp; "error": "InvalidQuery",

&nbsp; "message": "Query too short or invalid format",

&nbsp; "code": 400

}

```



\## Rate Limits

\- \*\*Free Tier\*\*: 100 queries/hour

\- \*\*Pro Tier\*\*: 1000 queries/hour

\- \*\*Enterprise\*\*: Unlimited

