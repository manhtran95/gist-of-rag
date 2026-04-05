# Gist of RAG

A minimal project to understand Retrieval Augmented Generation (RAG) using LangChain, OpenAI, and Pinecone.

## How it works

**Ingestion** (`ingestion.py`) — Load a text document, split it into chunks, embed each chunk with OpenAI, and store them in a Pinecone index.

**Retrieval** (`main.py`) — Embed the user query, search Pinecone for matching chunks, inject the results into a prompt, and send it to an LLM. Two implementations are included:
- Without LCEL — manual step-by-step chain
- With LCEL — declarative pipeline using LangChain Expression Language (recommended)

## Services

| Service | Role |
|---|---|
| [LangChain](https://www.langchain.com/) | RAG pipeline framework |
| [LangSmith](https://www.langchain.com/langsmith) | Monitoring and tracing |
| [OpenAI](https://platform.openai.com/docs/models) | LLM and embeddings |
| [Pinecone](https://www.pinecone.io) | Vector store |

## Environment variables

Create a `.env` file and fill in:

| Variable | Description |
|---|---|
| `OPENAI_API_KEY` | From [platform.openai.com](https://platform.openai.com) |
| `PINECONE_API_KEY` | From [pinecone.io](https://www.pinecone.io) |
| `INDEX_NAME` | Your Pinecone index name |
| `LANGCHAIN_API_KEY` | From [langchain.com/langsmith](https://www.langchain.com/langsmith) |
| `LANGCHAIN_PROJECT` | Your LangSmith project name |

## Quick start

```bash
# Install dependencies
uv sync

# Ingest documents into Pinecone
uv run ingestion.py

# Run the RAG query "What is Pinecone?"
uv run main.py
```
