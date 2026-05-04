# LangChain RAG Project

A question-answering demo using **LangChain** with **Retrieval-Augmented Generation (RAG)** powered by **Astra DB** Vector Search and **OpenAI** language models.

## Overview

This project demonstrates how to build a sophisticated PDF querying system that leverages:
- **Vector Search** for semantic similarity matching
- **LangChain** framework for orchestrating LLM workflows
- **Astra DB (Cassandra)** for scalable vector storage
- **OpenAI** for embeddings and language generation

## Features

- 📄 PDF document ingestion and processing
- 🔍 Semantic search using vector embeddings
- 🤖 LLM-powered question answering
- 💾 Persistent vector storage with Astra DB
- 🔄 RAG pipeline for accurate, context-aware responses

## Prerequisites

Before running this project, ensure you have:

1. **Python 3.8+** installed
2. **Astra DB Account** with a Serverless Cassandra database featuring Vector Search
   - Get a [Database Token](https://docs.datastax.com/en/astra-serverless/docs/vector-search/quickstart.html#_prepare_for_using_your_vector_database) with Database Administrator role
   - Note your Database ID and Region
3. **OpenAI API Key** for embeddings and language model access
   - Get it from [OpenAI Platform](https://platform.openai.com/api-keys)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Sekar-C-Mca/LangChain-Rag-Project.git
cd LangChain-Rag-Project
```

### 2. Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Key dependencies:
- `langchain` - LLM framework
- `cassio` - Astra DB integration
- `openai` - Embeddings and LLM API
- `PyPDF2` - PDF processing
- `datasets` - Data handling
- `tiktoken` - Token counting

## Configuration

### Environment Variables

Create a `.env` file in the project root:

```env
# Astra DB Configuration
ASTRA_DB_ID=your_database_id_here
ASTRA_DB_REGION=us-east1
ASTRA_DB_APPLICATION_TOKEN=your_token_here

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key_here
```

## Usage

### Running the Q&A Demo

```bash
jupyter notebook PDFQuery_LangChain.ipynb
```

The notebook demonstrates:
1. Setting up LangChain vector store with Astra DB
2. Loading and processing PDF documents
3. Creating embeddings for document chunks
4. Running a question-answering loop

### Example Query

```python
# Once the vector store is set up
question = "What is the main topic of this document?"
answer = qa_chain.run(question)
print(answer)
```

## Project Structure

```
LangChain-Rag-Project/
├── README.md              # Project documentation
├── LICENSE                # License file
├── PDFQuery_LangChain.ipynb # Main demo notebook
├── config/                # Configuration files
├── data/                  # Data storage
│   └── pdfs/             # PDF documents for processing
├── src/                   # Source code modules
├── tests/                 # Test files
└── .github/               # GitHub-specific files
    └── workflows/        # CI/CD workflows
```

## Architecture

### RAG Pipeline Flow

```
PDF Documents
     ↓
PDF Parser (PyPDF2)
     ↓
Text Chunking
     ↓
Embeddings (OpenAI)
     ↓
Vector Store (Astra DB)
     ↓
Query Processing
     ↓
Semantic Search
     ↓
Context Retrieval
     ↓
LLM (OpenAI) + Context
     ↓
Generated Answer
```

## Key Technologies

| Component | Technology | Purpose |
|-----------|-----------|---------|
| Vector Database | Apache Cassandra / Astra DB | Scalable vector storage |
| Embeddings | OpenAI | Convert text to vectors |
| LLM | OpenAI GPT | Generate answers |
| Framework | LangChain | Orchestrate workflows |
| PDF Processing | PyPDF2 | Extract text from PDFs |

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the License - see the [LICENSE](LICENSE) file for details.

## Support

For issues, questions, or suggestions, please open an [Issue](https://github.com/Sekar-C-Mca/LangChain-Rag-Project/issues) on GitHub.

## Acknowledgments

- [LangChain Documentation](https://python.langchain.com/)
- [Astra DB Vector Search](https://docs.datastax.com/en/astra-serverless/docs/vector-search/)
- [OpenAI API Documentation](https://platform.openai.com/docs/)
- [DataStax CassIO](https://cassio.org/)

---

**Author:** Sekar C
**Project:** LangChain RAG Project
**Last Updated:** May 2026
