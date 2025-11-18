# Personalized-tech-blogs-feeds
Tech Blog Knowledge Extractor: SLM + RAG + Knowledge Graph
This project builds a lightweight intelligence system that extracts, organizes, and summarizes technical knowledge from leading companies’ engineering blogs (Netflix, Airbnb, Uber).
The goal is to distill DS/ML, AI, and platform-engineering innovations into a structured, queryable knowledge base using:
Small Language Models (SLMs)
Retrieval-Augmented Generation (RAG)
Knowledge Graphs (KG)
Project Purpose
Modern tech companies publish valuable insights on DS/ML systems, experimentation platforms, embedding architectures, data engineering practices, and large-scale infrastructure designs. These posts are rich but difficult to track, compare, or summarize consistently.
This project aims to:
1. Automatically extract technical knowledge
Ingest engineering blog posts from Netflix, Airbnb, and Uber
Categorize content into DS/ML, AI, Data Engineering, Infrastructure, etc.
Extract concepts, workflows, patterns, architectures, and practical lessons
2. Build a structured knowledge graph
Identify entities, concepts, and relationships
Construct a graph showing connections between techniques, tools, and systems
Compare patterns across companies
3. Enable semantic search and question answering through RAG
Embed content and store in a vector database
Retrieve relevant documents for user queries
Provide structured, consistent explanations
4. Produce summaries and insights
Topic-level summaries
Cross-company comparison
Skills and system-design patterns relevant to DS/ML/MLE career development
Optional monthly update pipeline
System Architecture (High-Level)
Data Ingestion Pipeline
Collect blog posts
Parse text, metadata, and tags
Chunk and preprocess for downstream extraction
RAG Layer
Generate embeddings using an SLM
Store text and embeddings in a vector database
Retrieve relevant context for queries
Knowledge Graph Construction
Extract entities and relations from texts
Build triplets (subject–relation–object)
Store in a graph database such as Neo4j
Query and Summarization Engine
Hybrid retrieval (vector + KG)
Structured answers and summaries
Optional interactive interface (Streamlit)

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
├── README.md
Technologies and Tools
Small Language Models for extraction and summarization
Embedding models such as MiniLM, Instructor, or GTE
Vector databases (Chroma or FAISS)
Knowledge graph storage (Neo4j, NetworkX, or RDF)
Python-based ingestion pipeline
Optional Streamlit interface
Data Sources
This project uses publicly available technical blog posts, including but not limited to:
Netflix Tech Blog
Airbnb Engineering & Data Science
Uber Engineering
No restricted, proprietary, or commercial data is collected.
Future Work
Evaluate multiple SLMs for extraction consistency
Expand KG ontology and entity linking
Add trend analysis over time
Integrate visualization for KG exploration
Build automated monthly ingestion pipeline
