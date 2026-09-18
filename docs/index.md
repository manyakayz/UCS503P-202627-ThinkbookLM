# ThinkBook LM

**ThinkBook LM** is an AI-powered document research and knowledge management platform that allows users to upload documents, organize them into notebooks, and retrieve relevant information from their content.

The project is designed around a local-first AI pipeline using document processing, embeddings, vector search, and retrieval.

---

## Features

* **Notebook-based organization**
  Organize uploaded documents into separate notebooks.

* **Document ingestion**
  Upload documents and extract their text for processing.

* **Semantic search**
  Convert document content into embeddings and retrieve relevant passages using vector similarity search.

* **Local AI infrastructure**
  Uses locally hosted models through Ollama where applicable, reducing dependency on external AI APIs.

* **Persistent storage**
  PostgreSQL is used for application data, while ChromaDB is used for vector storage and semantic retrieval.

* **Modern web interface**
  Built with React and Vite for a responsive frontend experience.

---

## System Architecture

The current application consists of three primary components:

```text
                    ┌─────────────────────┐
                    │      React UI       │
                    │    (Vite + React)   │
                    └──────────┬──────────┘
                               │
                               │ HTTP / API
                               ▼
                    ┌─────────────────────┐
                    │    FastAPI Server   │
                    │      Backend        │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
                 ▼                           ▼
        ┌─────────────────┐        ┌─────────────────┐
        │   PostgreSQL    │        │    ChromaDB     │
        │                 │        │                 │
        │ Users           │        │ Embeddings      │
        │ Notebooks       │        │ Vector Search   │
        │ Documents       │        │                 │
        └─────────────────┘        └─────────────────┘
                                         │
                                         ▼
                                ┌─────────────────┐
                                │      Ollama     │
                                │  Local AI Model │
                                └─────────────────┘
```

---

## Document Processing Pipeline

When a document is uploaded, it goes through the following general pipeline:

```text
Document Upload
      │
      ▼
Text Extraction
      │
      ▼
Text Chunking
      │
      ▼
Embedding Generation
      │
      ▼
ChromaDB
      │
      ▼
Semantic Retrieval
      │
      ▼
Relevant Document Context
```

This allows the application to search documents based on **meaning and context**, rather than relying only on exact keyword matches.

---

## Technology Stack

### Frontend

* React
* Vite
* JavaScript
* CSS

### Backend

* Python
* FastAPI
* REST APIs

### Databases

* PostgreSQL
* ChromaDB

### AI / ML

* Ollama
* Embedding models
* Vector similarity search

### Development & Deployment

* Git
* GitHub
* GitHub Actions
* GitHub Pages for project documentation

---

## Project Structure

```text
ThinkBookLM/
│
├── code/
│   ├── frontend/
│   │   └── ...
│   │
│   └── backend/
│       └── ...
│
├── docs/
│   └── index.md
│
├── .github/
│   └── workflows/
│       └── ...
│
├── README.md
└── ...
```

---

## Getting Started

### 1. Clone the repository

```bash
git clone <repository-url>
cd ThinkBookLM
```

### 2. Start the backend

Navigate to the backend directory and install the required dependencies according to the project's backend configuration.

```bash
cd code/backend
```

Start the FastAPI application using the project's configured development command.

### 3. Start the frontend

```bash
cd code/frontend
npm install
npm run dev
```

The frontend will then be available through the Vite development server.

---

## Development Workflow

The project follows a typical frontend/backend development workflow:

```text
Developer
    │
    ▼
Git Repository
    │
    ├──────────────► Frontend Development
    │
    ├──────────────► Backend Development
    │
    └──────────────► Documentation
                          │
                          ▼
                    GitHub Actions
                          │
                          ▼
                     GitHub Pages
```

Documentation is built automatically through **GitHub Actions** and deployed to **GitHub Pages** whenever changes are pushed to the configured repository branch.

---

## Project Status

ThinkBook LM is currently under active development.

The core infrastructure for:

* frontend application
* backend API
* document processing
* database storage
* vector storage
* semantic retrieval

is being developed as part of the project.

Additional AI-powered capabilities can be integrated on top of the existing retrieval pipeline as development continues.

---

## License

This project is developed for academic and educational purposes.
