# 🧠 RAG & Embeddings Toolkit

[![Python Version](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

A comprehensive suite of demos and CLI tools demonstrating how to build a Retrieval-Augmented Generation (RAG) pipeline and work with embeddings using HuggingFace & ChromaDB—no OpenAI required.

## 🚀 Features

- **RAG Data Store Generator**: Load Markdown → Chunk text → Compute embeddings → Persist to ChromaDB
- **Word Comparison Tool**: Compute and compare word embeddings using cosine similarity, cosine distance, and Euclidean distance
- **RAG Query System Demo**: Semantic search over your ChromaDB store with context-based answers via CLI or interactive REPL

## 📂 Repository Structure

```
.
├── chroma/                          # ⛔ Persisted vector store (gitignored)
├── Rag_proto.ipynb                  # 📓 Main Jupyter notebook with all RAG components
├── requirements.txt                 # Pinned dependencies
├── .gitignore                       # Excluded files & directories
└── README.md                        # This file
```

## ⚙️ Prerequisites

- Python **3.10+**
- Jupyter Notebook or JupyterLab
- Git
- (Optional) GPU & CUDA for faster embeddings

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/rag-embeddings-toolkit.git
cd rag-embeddings-toolkit
```

### 2. Create & Activate Virtual Environment

```bash
python -m venv .venv

# macOS/Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Configure Environment (Optional)

```bash
# Only needed if integrating external APIs later
cp .env.example .env
```

## 📦 Usage

### Getting Started

1. **Open the Jupyter Notebook**
   ```bash
   jupyter notebook Rag_proto.ipynb
   ```
   
2. **Run the notebook cells sequentially** to:
   - Set up dependencies and imports
   - Generate the RAG data store
   - Compare word embeddings  
   - Query the RAG system

### Notebook Sections

The `Rag_proto.ipynb` notebook contains three main components:

#### 1. RAG Data Store Generator
- Loads text data (markdown or other formats)
- Splits text into 300-character chunks with 100-character overlap
- Computes embeddings using HuggingFace's `all-MiniLM-L6-v2` model
- Persists the ChromaDB store under `chroma/`

#### 2. Word Comparison Tool
- Calculates cosine similarity, cosine distance, and Euclidean distance
- Provides interpretive results (e.g., "Very similar", "Quite different")
- Runs batch tests across categories (animals, colors, etc.)

#### 3. RAG Query System
- Embeds your questions into vector space
- Retrieves top-K most relevant passages
- Displays context with relevance scores
- Supports interactive querying

## 🔧 Customization

All customization can be done within the `Rag_proto.ipynb` notebook:

- **Data Sources**: Modify the data loading cells to point to your text files
- **Chunk Settings**: Adjust `chunk_size` & `chunk_overlap` parameters in the text splitting section
- **Embedding Model**: Change the HuggingFace model in the embedding generation cells
- **Relevance Thresholds**: Modify relevance-score cutoffs in the query system section
- **Query Parameters**: Adjust the number of retrieved results (top-K) in query cells

## 📁 Key Components

### Data Store Generator
Processes markdown documents and creates a searchable vector database using:
- **Text Splitting**: Recursive character-based chunking
- **Embeddings**: HuggingFace sentence transformers
- **Storage**: ChromaDB for efficient similarity search

### Word Comparison Tool
Demonstrates embedding similarity metrics:
- **Cosine Similarity**: Measures directional similarity (0-1)
- **Cosine Distance**: Inverse of cosine similarity (0-2)
- **Euclidean Distance**: Geometric distance in embedding space

### Query System
Implements semantic search with:
- **Question Embedding**: Transforms queries into vector space
- **Similarity Search**: Finds most relevant document chunks
- **Context Assembly**: Combines results for comprehensive answers

## 🔍 Example Usage

Once you have the notebook running:

1. **Execute the setup cells** to install dependencies and import libraries
2. **Run the data store generation section** to create your vector database
3. **Try the word comparison examples** to understand embedding similarities
4. **Use the query system** to ask questions about your data

Example queries you can try:
- "What are the main topics discussed?"
- "Find information about [specific concept]"
- "Summarize the key points"

## ⚠️ Important Files (.gitignore)

```gitignore
# Virtual environments
.venv/
venv/
env/

# Vector store (can be large)
chroma/

# Environment files
.env
.env.local

# OS & IDE files
.DS_Store
.vscode/
__pycache__/
*.pyc
*.pyo
*.pyd

# Jupyter Notebook checkpoints
.ipynb_checkpoints/
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Related Resources

- [HuggingFace Transformers](https://huggingface.co/docs/transformers/)
- [ChromaDB Documentation](https://docs.trychroma.com/)
- [LangChain Text Splitters](https://python.langchain.com/docs/modules/data_connection/document_transformers/)

## 📧 Support

If you encounter any issues or have questions, please:
1. Check existing [Issues](https://github.com/<your-username>/rag-embeddings-toolkit/issues)
2. Create a new issue with detailed information
3. Include your Python version and system details
