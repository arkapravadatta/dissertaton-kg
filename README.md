This repository contains the implementation and experimental study for the M.Tech (AI & ML) dissertation.

The core objective of this work is to analyze the limitations of vector-only Retrieval-Augmented Generation (RAG) systems when handling enterprise queries that involve explicit relationships, hierarchies, constraints, and temporal validity, and to evaluate how an explicit Knowledge Graph (KG) representation can improve factual correctness and completeness.

The project uses synthetic but realistic HR and enterprise datasets sourced from Kaggle and GitHub, ensuring reproducibility and controlled experimentation. A baseline vector RAG pipeline is implemented using open-source sentence-transformer embeddings and an in-memory FAISS vector store. In parallel, a deterministic enterprise Knowledge Graph is constructed in Neo4j, explicitly modeling entities such as employees, positions, departments, and their relationships, including reporting hierarchy and time-bound role assignments.

The Knowledge Graph serves as a structured ground truth for evaluating query answering behavior. Comparative experiments focus on query categories that are challenging for vector-based retrieval, such as:

Range and numerical constraints (e.g., salary filters)

Multi-hop relational queries (e.g., reporting structure)

Temporally bounded queries (e.g., roles held within a specific time period)

The repository also explores the use of LangChain Experimental’s LLMGraphTransformer as an automated knowledge extraction layer, while keeping the core evaluation independent of any single LLM or API.

This work does not aim to propose new language models, but instead emphasizes representation-level reasoning, reproducible evaluation, and clear identification of failure modes in vector-only RAG systems. The findings are intended to inform the design of hybrid retrieval architectures combining semantic recall with structured grounding.
