## Gist of RAG

### Idea
This project helps the understanding of Retrieval Augmented Generation.

** Ingestion
We will load a Medium blog, split it into chunks, turn the chunks into embeddings and insert into a vector store's index.

** Retrieval
We will turn user query into embedding, search against the vector store's index and return the matching chunks. The returned chunks will be added to the prompt before the prompt is sent to LLM together with the query, helping the LLM to answer the query with augmented information.

### Services
Langchain framework for building AI agent.
Langsmith for monitoring AI agent workflow.
Embedding: OpenAI Embedding or Ollama Embedding.
Pinecone as Vector Store.

### Set up
** LLM
Register an account with OpenAI or Ollama to get their API key.
** Embedding
You can use OpenAI embedding model by setting OPENAI_API_KEY, or Ollama embedding model by setting OLLAMA_EMBEDDING_MODEL.
** Monitoring
Register an account with Langsmith, create a project, create an API key and add them to your .env file.
** Pinecone
Register an account with Pinecone, create an index and an API key and add them to your .env file.