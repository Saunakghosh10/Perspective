# Chroma VectorDB Integration

This document describes the integration of Chroma as the vector database for semantic embeddings in the Perspective project.

## Overview

The integration provides a FastAPI-based API for storing and retrieving semantic embeddings using Chroma VectorDB. This enables efficient storage and similarity search of text embeddings for features like Counter-Perspective Generation and Real-Time Analysis.

## API Endpoints

### 1. Store Document (`POST /store`)
Stores a document's text and its semantic embedding in Chroma.


Example request:
```json
{
  "text": "Climate change is a significant global challenge that requires immediate action.",
  "metadata": {
    "source": "test",
    "category": "environment"
  }
}
```

### 2. Search Similar Documents (`POST /search`)
Search for documents similar to the query text based on embeddings.


Example request:
```json
{
  "text": "What are the benefits of renewable energy?",
  "n_results": 2
}
```

### 3. Health Check (`GET /health`)
Check if the API and database are healthy.


## Implementation Details

- Uses `sentence-transformers/all-MiniLM-L6-v2` for generating text embeddings
- Persistent storage in `./chroma_data` directory
- Built with FastAPI for high performance and automatic API documentation
- Integrates with LangChain for embedding generation

## Testing the API

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Start the server:
```bash
uvicorn app.main:app --reload
```

3. Visit http://127.0.0.1:8000/docs for interactive API documentation

## Screenshots
