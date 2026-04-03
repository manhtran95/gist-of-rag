# Gist of RAG

## Idea
This project helps the understanding of Retrieval Augmented Generation.

### Ingestion
We will load a Medium blog, split it into chunks, turn the chunks into embeddings and insert into a vector store's index.

### Retrieval
We will turn user query into embedding, search against the vector store's index and return the matching chunks. The returned chunks will be added to the prompt before the prompt is sent to LLM together with the query, helping the LLM to answer the query with augmented information.

## Services
* **[LangChain](https://www.langchain.com/)** framework for building AI agents.
* **[LangSmith]** for monitoring AI agent workflows.
* **[LLM]** OpenAI(see model list at https://developers.openai.com/api/docs/models) or Ollama(see model list at https://ollama.com/search).
* **[Embedding]** OpenAI Embedding or Ollama Embedding.
* **[Pinecone]** as Vector Store.

## Environment variables
#### LLM
Register an account with OpenAI(https://developers.openai.com) or Ollama(https://ollama.com) to get their API key.
#### Embedding
You can use OpenAI embedding model by setting OPENAI_API_KEY, or Ollama embedding model by setting OLLAMA_EMBEDDING_MODEL, full list here (https://docs.ollama.com/capabilities/embeddings).
#### Monitoring
Register an account with Langsmith(https://www.langchain.com/langsmith), create a project, create an API key and add them to your .env file.
#### Pinecone
Register an account with Pinecone(https://www.pinecone.io), create an index and an API key and add them to your .env file.

## Quick Start

1.  **Initialize Project**
    ```bash
    uv init
    ```

2.  **Add Dependencies**
    Install the necessary packages in pyproject.toml:
    ```bash
    uv lock
    uv sync
    ```

3.  **Setup Environment**
    Copy the `.env.example` to `.env` and fill in your keys.

4.  **Run the Application**
    Use `uv run` to automatically load the virtual environment and `.env` file:
    ```bash
    uv run main.py
    ```