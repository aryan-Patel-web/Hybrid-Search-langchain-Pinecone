# 🔍 Hybrid Search with LangChain and Pinecone

This project demonstrates how to build **hybrid search** combining:

✅ Sparse search (BM25)  
✅ Dense vector embeddings  
✅ Pinecone vector index  
✅ LangChain retrievers  

It’s perfect for improving retrieval in RAG pipelines where semantic and keyword relevance matter.

---

## 🚀 Features

- Build a **hybrid retriever** for improved search
- Use BM25 (sparse) + embeddings (dense) together
- Save and reload BM25 encoder states
- Integrate with LangChain’s PineconeHybridSearchRetriever
- Serverless Pinecone deployment (AWS region)

---

## 📚 How it Works

1. Create a Pinecone index (if it doesn’t exist).
2. Compute embeddings for your data.
3. Compute BM25 sparse vectors for the same data.
4. Store BM25 encoder values to disk.
5. Load the encoder for future use.
6. Use LangChain’s `PineconeHybridSearchRetriever` for hybrid retrieval.

---

## 🛠️ Installation

Install dependencies:

```bash
pip install pinecone-client pinecone-text langchain langchain-community


🔧 Environment Variables
Create a .env file:

PINECONE_API_KEY=YOUR_PINECONE_API_KEY


# Add texts to hybrid retriever
retriever.add_texts([
    "In 2023, I visited Paris",
    "In 2022, I visited New York",
    "In 2021, I visited New Orleans"
])

# Query it
result = retriever.invoke("What city did I visit first?")
print(result)

Answer --

"In 2021, I visited New Orleans"



