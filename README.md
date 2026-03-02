# 🔹 Modular RAG Framework

**Production-ready modular RAG framework** with pluggable components for enterprise AI systems.

---

## 🏢 Simulated Client Use Case

> SaaSCo Inc. wants to deploy multiple RAG-powered assistants across teams (Support, HR, Legal) with a single, configurable framework.

**Requirements:**

- Multi-team support
- Pluggable vector DB
- Multiple LLMs support
- Consistent evaluation
- Secure multi-tenant design

---

## 🏗 Architecture Overview

```text
config/
  └─ config.yaml       # Top-level configuration
core/
  ├─ ingestion/        # Document parsing & chunking
  ├─ embeddings/       # Multi-model embeddings
  ├─ retrievers/       # Vector, hybrid, reranker
  ├─ generators/       # LLM abstraction
  ├─ evaluation/       # Metrics & benchmarking
  └─ utils/            # Logging, monitoring, helpers
api/
  └─ fastapi_service.py
docker/
  └─ docker-compose.yml
```

**Pluggable Design Highlights:**

- Switch vector DBs: Qdrant, Weaviate, Chroma  
- Swap LLM models: OpenAI, BGE, E5, Instructor  
- Config-driven pipeline → no code changes to switch tenants  
- Evaluation integrated for every retrieval strategy

---

## 🔹 Key Features

- Hybrid + vector retrieval
- Cross-encoder reranking support
- Multi-tenant simulation
- Logging & metrics built-in
- Dynamic configuration

---

## 💻 Installation

```bash
git clone https://github.com/JEMAIZ/modular-rag-framework.git
cd modular-rag-framework
docker-compose up --build
```

---

## 🧠 Example Usage

```python
from core.retrievers.hybrid import HybridRetriever
from core.embeddings.embed_models import EmbeddingModel

retriever = HybridRetriever(config="config/config.yaml")
embedding_model = EmbeddingModel(model_name="bge")
results = retriever.query("How to onboard new employees?")
```

---

## 📊 Simulated Metrics

| Component           | Success Rate | Latency (s) |
|--------------------|--------------|-------------|
| Retrieval           | 0.91         | 1.4         |
| Hybrid + Reranker   | 0.94         | 1.5         |
| Embedding swap test | 0.92         | 1.3         |

---

## 📝 Future Improvements

- Add dynamic top-k selection  
- Include active learning for reranker  
- Full orchestration on Kubernetes  
- Multi-language support

---

## 🤝 Contact

Available for **RAG framework consulting**, **multi-team deployment**, and **enterprise architecture advisory**.
