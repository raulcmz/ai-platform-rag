# AI Platform RAG

A production-style Retrieval-Augmented Generation platform, built to apply Kubernetes-native platform engineering patterns (already used for LLM serving in [`k8s-llmops-inference-platform`](https://github.com/raulcmz/k8s-llmops-inference-platform)) to a retrieval + generation stack.

## Status: 🧭 Design phase

No code yet — this repository currently holds the scope and architecture this project will implement. It will follow the same bar as the other lab projects in this account: tests, CI, and honest "done / not done yet" tracking in the README as it grows.

## Planned scope

- **Ingestion & indexing** — document loading, chunking, and embedding generation
- **Vector search** — a self-hosted vector store for semantic retrieval
- **Self-hosted LLM integration** — reusing the gateway/backend-adapter pattern from `k8s-llmops-inference-platform` (Ollama/vLLM)
- **API-driven architecture** — a stable retrieval + generation API, decoupled from the underlying vector store and model backend
- **Containerized services** — each component (ingestion, retriever, gateway) shipped as its own container image
- **Kubernetes deployment** — Helm-based deployment, consistent with the rest of the account's platform-engineering projects
- **Observability** — Prometheus metrics for retrieval latency, hit rate, and generation quality, following the metrics conventions used in `k8s-llmops-inference-platform`

## Explicitly out of scope (for v1)

- Multi-tenant access control / auth
- Managed/hosted vector databases
- Fine-tuning of the underlying LLM

## Why this project

Most public RAG tutorials stop at "call an API and get an answer." This project focuses on the platform engineering problem instead: how do you run retrieval and generation as a reliable, observable, horizontally-scalable Kubernetes service, with the same operational rigor (health/readiness semantics, metrics, CI) as any other production workload.

## License

See [LICENSE](LICENSE).
