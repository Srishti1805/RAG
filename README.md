# RAG (Retrieval Augmented Generation) Project

This repository demonstrates an implementation of Retrieval Augmented Generation (RAG) using Python and Langchain. The project is designed to answer questions by retrieving relevant context from documents and generating answers using large language models (LLMs) like OpenAI's GPT.

## Features

- **Document Loading**: Load PDF and text documents from a specified local directory.
- **Text Chunking**: Split loaded documents into smaller, overlapping chunks for efficient embedding and retrieval.
- **Embedding & Vector Store**: Use OpenAI embeddings and store chunks in a Chroma vector database for fast similarity search.
- **RAG Workflow**: Retrieve the most relevant document snippets given a user query, and use an LLM to generate answers based strictly on retrieved context.
- **Source Attribution**: For each answer, the source documents are listed to ensure transparency.
- **Environment Management**: Uses `.env` files to securely store API keys.

## Installation

Install the required Python packages:

```bash
pip install langchain
pip install unstructured
pip install tiktoken
pip install openai
pip install chromadb
pip install -U langchain-community
```

## Usage

1. **Set Up Your Documents**: Place your PDF/text files in the `files` directory.
2. **Environment Variables**: Create a `.env` file and add your OpenAI API key.

   ```
   OPENAI_API_KEY=your_api_key_here
   ```

3. **Run the Notebook**: Open and execute `RAG_Srishti.ipynb` step by step.

   - Documents are loaded and split into chunks.
   - Chunks are embedded and stored in Chroma.
   - Query the system with natural language questions.
   - The system retrieves relevant chunks and generates an answer using the LLM.

4. **Sample Query**:

   ```python
   query_text = "which tablets do you have"
   ```

   The system will retrieve relevant context and use the prompt template to answer your question.

## Core Files

- `RAG_Srishti.ipynb`: Main Jupyter notebook demonstrating the RAG workflow.
- `files/`: Directory containing source documents for retrieval.

## Technologies Used

- Python
- Langchain
- OpenAI API
- ChromaDB
- Jupyter Notebook

## How It Works

1. **Load Documents**: The notebook uses Langchain's `DirectoryLoader` to load PDFs or text files from the specified directory.
2. **Split Text**: Documents are split into manageable chunks with overlap using `RecursiveCharacterTextSplitter`.
3. **Embedding & Storage**: Chunks are embedded using OpenAI embeddings and stored in ChromaDB.
4. **Query & Retrieve**: When a question is asked, the system retrieves the most relevant chunks based on semantic similarity.
5. **Generate Answer**: The retrieved context is passed to an LLM which generates an answer constrained to only the provided context.

## Example Output

```
Response: [Generated answer by LLM]
Sources: [List of source documents]
```

## License

This project is for educational and research purposes.

---

Feel free to modify the notebook for your own document types, embedding models, or LLM providers!
