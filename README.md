# Agentic Workflow Orchestrator & Dashboard

A visual **node-edge graph** editor for **LangGraph** and LangChain-style workflows. Build and run agent workflows in a web UI, backed by a FastAPI server, using local LLMs (e.g. Ollama) or online APIs.

Full documentation: [LangGraph-GUI.github.io](https://LangGraph-GUI.github.io)

![Cover](https://langgraph-gui.github.io/cover.webp)

## Features

- **Visual graph editor** — SvelteFlow-based UI to design and edit LangGraph workflows
- **Run workflows** — Execute graphs with a local LLM (Ollama) or remote API
- **Docker Compose** — Single-command stack: backend, frontend, optional Ollama
- **Kubernetes** — Manifests under `/k8s` for deployment to a cluster
- **Electron** — Optional desktop app build

## Prerequisites

- **Docker Compose**
- (Optional) **NVIDIA Container Toolkit** for GPU-accelerated Ollama
- (Optional) **npm** for Electron build

Windows setup: [LangGraph GUI Setup on Windows](https://langgraph-gui.github.io/Setup/Windows)

## Getting Started

### Using the repo

Clone the repository (no submodules required if you have a full copy):

```bash
cd LangGraph-GUI
```

### Docker Compose

Build and start services. To use Ollama, pull a model first:

```bash
docker compose build
docker compose up ollama -d
docker compose exec ollama ollama pull <model-name>
docker compose down
```

Then start the full stack:

```bash
docker compose up
```

Open [http://localhost:3000](http://localhost:3000) to use the graph editor and run workflows.

### Kubernetes

See the [/k8s](/k8s) directory for deployment manifests.

## Project layout

- **frontend** — SvelteFlow-based graph UI
- **backend** — FastAPI server; runs and manages workflow execution
- **examples** — Sample LangGraph definitions
- **electron** — Desktop app wrapper
- **k8s** — Kubernetes manifests
- **ollama** / **nginx** — Service configs for Docker

## Contributing

Suggestions, bugs, and questions: use [Discussions](https://github.com/LangGraph-GUI/LangGraph-GUI/discussions) or [Issues](https://github.com/LangGraph-GUI/LangGraph-GUI/issues).

## License

MIT. See [LICENSE](LICENSE).
