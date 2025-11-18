# Tech Blog Knowledge Extractor: SLM + RAG + Knowledge Graph

This repository implements a lightweight intelligence system that extracts, organizes, and summarizes technical knowledge from engineering blogs published by Netflix, Airbnb, and Uber.  
The project focuses on distilling DS/ML, AI, and platform-engineering innovations into a structured, queryable knowledge base using:

- Small Language Models (SLMs)
- Retrieval-Augmented Generation (RAG)
- Knowledge Graphs (KG)

## Project purpose

Engineering blogs from major tech companies publish valuable, practical systems knowledge, but the information is scattered, inconsistent, and hard to compare. This project aims to:

1. Automatically ingest and categorize blog posts into DS/ML, Data Engineering, AI Infrastructure, and other themes.  
2. Extract entities, relationships, workflows, and system design patterns into a knowledge graph.  
3. Index the content in a vector database to support semantic search and RAG-based querying.  
4. Produce summaries, topic-level insights, and optional monthly reports to track evolving engineering patterns.

## System architecture (high-level)

**1. Data ingestion**  
Fetch blog posts from Netflix, Airbnb, and Uber; parse text and metadata; clean and chunk text.

**2. RAG layer**  
Generate embeddings using an SLM; store text and embeddings in a vector database; retrieve relevant chunks.

**3. Knowledge graph**  
Extract entities and relations; construct a graph using triplets (subject–relation–object); enable relation queries.

**4. Query and summarization engine**  
Hybrid retrieval using both vector search and graph traversal; provide structured explanations and comparisons.

**5. Presentation layer**  
Optional Streamlit app for search, visualization, and summarization.

## Project structure

```
tech-blog-knowledge-extractor/
│
├── data/
│   ├── raw/                 # Unprocessed blog posts
│   ├── processed/           # Cleaned, chunked text
│   └── metadata/            # Tags, dates, categories
│
├── ingestion/
│   ├── fetch_netflix.py
│   ├── fetch_airbnb.py
│   ├── fetch_uber.py
│   └── clean_text.py
│
├── rag/
│   ├── embedder.py          # Embedding model wrapper
│   ├── vectorstore.py       # Vector DB operations
│   └── retriever.py
│
├── knowledge_graph/
│   ├── entity_extraction.py
│   ├── relation_extraction.py
│   ├── graph_builder.py
│   └── neo4j_interface.py
│
├── summaries/
│   ├── summarize_topics.py  # DS/ML, AI Infra, Data Eng, etc.
│   ├── compare_companies.py
│   └── monthly_report.py
│
├── app/
│   └── streamlit_app.py     # Optional UI for search and summarization
│
├── configs/
│   ├── model_config.yaml
│   ├── ingestion_config.yaml
│   └── graph_config.yaml
│
├── notebooks/
│   ├── exploratory_analysis.ipynb
│   └── demo_queries.ipynb
│
├── tests/
│   └── test_extraction.py
│
├── requirements.txt
└── README.md
```
