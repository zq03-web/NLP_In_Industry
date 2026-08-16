```markdown
# NLP in Industry - Multi-Hop QA with RAG

This repository contains experiments on multi-hop question answering using the HotpotQA dataset.

We compare three retrieval strategies:

- **RAG.ipynb**  
  Implements a standard dense Retrieval-Augmented Generation (RAG) pipeline.  
  It also includes Direct GPT-4o and Full Context baselines.

- **AgenticRAG.ipynb**  
  Implements an iterative Agentic RAG approach.  
  The LLM decides whether the retrieved evidence is sufficient or whether an additional search with a reformulated query is required.

- **GraphRAG.ipynb**  
  Implements a GraphRAG pipeline using a shared corpus.  
  Documents are organized through entities, relationships, and graph communities, and questions are answered using local graph search.

## Dataset

Experiments are based on the **HotpotQA distractor validation set**, which is designed for multi-hop question answering.

## Evaluation

The main evaluation metrics are:

- Exact Match (EM)
- Token-level F1

## Main Results

| Method | EM | F1 |
|---|---:|---:|
| Direct GPT-4o | 0.360 | 0.494 |
| Vanilla RAG | 0.340 | 0.498 |
| Full Context | 0.490 | 0.653 |
| Agentic RAG | **0.600** | **0.726** |
| GraphRAG* | 0.480 | 0.659 |

\* GraphRAG uses a different hard-bridge subset and a shared retrieval corpus, so its results are not directly comparable with the other systems.

## Project Goal

The goal of this project is to study how different retrieval strategies affect multi-hop question answering, especially whether adaptive or graph-based retrieval can improve evidence acquisition compared with single-stage RAG.
```
