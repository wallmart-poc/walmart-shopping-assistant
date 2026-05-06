# walmart-shopping-assistant · Shopping Assistant Service

Optional AI-powered shopping assistant HTTP service. Accepts natural-language queries and returns product recommendations using Gemini and AlloyDB vector search.

## Stack
- **Language:** Python 3.11
- **Framework:** Flask
- **AI:** Google Gemini (`langchain-google-genai`)
- **Vector store:** AlloyDB (`langchain-google-alloydb-pg`)
- **Secrets:** Google Secret Manager

## API
- `POST /ask` — accepts a JSON body `{"query": "..."}` and returns a conversational product recommendation

## Running locally
Requires a Google Cloud project with AlloyDB and Secret Manager configured.

```bash
pip install -r requirements.txt
python shoppingassistantservice.py
```

Service listens on port `8080` by default.

## Dependencies
Connects to external managed services only — no internal gRPC service calls:
- Google Gemini API (via LangChain)
- AlloyDB vector store (pre-populated with product embeddings)
- Google Secret Manager (for credentials)

