# Tech Blog Knowledge Extractor: SLM + RAG + Knowledge Graph

This repository implements a lightweight intelligence system that extracts, organizes, and summarizes technical knowledge from engineering blogs (Netflix, Airbnb, Uber).  
The project is focused on distilling DS/ML, AI, and platform-engineering innovations into a structured, queryable knowledge base using:

- Small Language Models (SLMs)
- Retrieval-Augmented Generation (RAG)
- Knowledge Graphs (KG)

## Project purpose

Engineering blogs from major tech companies publish valuable, practical systems knowledge that is often scattered and hard to compare. This project aims to:

1. Automatically ingest and categorize blog posts (DS/ML, Data Engineering, Infrastructure, etc.).  
2. Extract entities, relations, and system patterns and store them in a knowledge graph.  
3. Index content for semantic retrieval and support RAG-based Q&A.  
4. Produce concise summaries and monthly insights to help practitioners learn industry patterns quickly.

## System architecture (high-level)

1. Data ingestion: fetch blog posts and metadata, clean and chunk text.  
2. RAG layer: create embeddings, store chunks in a vector database, enable retrieval.  
3. Knowledge graph: extract triplets (subject–relation–object) and build a graph for relation queries and cross-company comparison.  
4. Query engine: hybrid retrieval (vector + KG) to generate grounded answers and summaries.  
5. Presentation: optional Streamlit UI, static site, and monthly reports.

## Project structure

ech-blog-knowledge-extractor/
│
├── data/
│ ├── raw/ # Unprocessed blog posts
│ ├── processed/ # Cleaned, chunked text
│ └── metadata/ # Tags, dates, categories
│
├── ingestion/
│ ├── fetch_netflix.py
│ ├── fetch_airbnb.py
│ ├── fetch_uber.py
│ └── clean_text.py
│
├── rag/
│ ├── embedder.py # Embedding model wrapper
│ ├── vectorstore.py # Vector DB operations
│ └── retriever.py
│
├── knowledge_graph/
│ ├── entity_extraction.py
│ ├── relation_extraction.py
│ ├── graph_builder.py
│ └── neo4j_interface.py
│
├── summaries/
│ ├── summarize_topics.py # DS/ML, AI Infra, Data Eng, etc.
│ ├── compare_companies.py
│ └── monthly_report.py
│
├── app/
│ └── streamlit_app.py # Optional UI for search and summarization
│
├── configs/
│ ├── model_config.yaml
│ ├── ingestion_config.yaml
│ └── graph_config.yaml
│
├── notebooks/
│ ├── exploratory_analysis.ipynb
│ └── demo_queries.ipynb
│
├── tests/
│ └── test_extraction.py
│
├── requirements.txt
└── README.md
