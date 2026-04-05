# 🧠 FahMai RAG Challenge (SuperAI Engineer)

An advanced AI evaluation pipeline focusing on Retrieval-Augmented Generation (RAG). This project was developed to accurately retrieve context and generate precise answers for domain-specific questions during the SuperAI Engineer Hackathon.

## 🏆 Performance
* **Metric:** Accuracy (Percentage of correct answers)
* **My Private Score:** `0.87` (87%)
* **Competition Baseline:** `0.80` (80%)
* **Result:** Outperformed the baseline by 7% through optimized retrieval strategies and an ensemble prediction mechanism.

## 🛠️ Tech Stack
* **Core Technologies:** `Python`, `Large Language Models (LLMs)`
* **RAG Architecture:** Vector Search, Semantic Embedding, Context Retrieval
* **Data Processing:** `Pandas`, `JSON`, `CSV`
* **Optimization:** Prompt Engineering, Ensemble/Majority Voting

## ⚙️ Data Pipeline & Methodology

Building a robust RAG system requires more than just calling an LLM API. Our pipeline is structured into 4 main phases:

### 1. Document Processing & Chunking
* Parsed and preprocessed complex source documents.
* Applied optimal text chunking strategies to ensure that the semantic context is preserved while fitting within the embedding model's context window.

### 2. Semantic Retrieval
* Converted document chunks into dense vector representations.
* Implemented a similarity search mechanism to retrieve the top-K most relevant chunks based on the user's specific query.

### 3. LLM Generation & Prompt Optimization
* Crafted highly specific system prompts to instruct the LLM to rely strictly on the retrieved context, heavily reducing AI hallucination.
* Passed the retrieved context and user query into the LLM to formulate the final answer.

### 4. Ensemble & Post-processing (The Winning Strategy)
* **Voting Mechanism:** Instead of relying on a single generated response, the pipeline aggregated multiple prediction runs.
* Utilized `Counter` to determine the most frequent/best prediction (`best_preds`) for each question ID.
* Successfully mapped and formatted the final outputs into a structured `submission.csv` for evaluation.

## 🚀 Future Improvements
* Integrating advanced reranking models (e.g., Cross-Encoders) to further refine the retrieved contexts.
* Experimenting with Hybrid Search (Keyword + Vector Search) to handle highly specific entity queries.
