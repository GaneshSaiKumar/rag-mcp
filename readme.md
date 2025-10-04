# RAG MCP Project

This project is a simple implementation of a Retrieval-Augmented Generation (RAG) system based on a "Model Context Protocol" design pattern. It uses a local knowledge base to provide context-aware answers to user queries.

---

## 🚀 Features

-   **Document Loading**: Loads and processes PDF files from a local `data` directory.
-   **Text Chunking**: Splits documents into manageable chunks for embedding.
-   **Vector Embeddings**: Uses Hugging Face's `all-MiniLM-L6-v2` model to create embeddings locally.
-   **Vector Storage**: Utilizes `ChromaDB` for efficient, local vector storage and retrieval.
-   **RAG Chain**: Implements a complete RAG pipeline using `LangChain` to answer questions based on the document's content.

---

## 🛠️ Setup & Installation

1.  **Clone the repository (or set up the folder):**
    Ensure you have all the project files in a local directory.

2.  **Create a data folder:**
    ```bash
    mkdir data
    ```
    Place your PDF document(s) inside this `data` folder.

3.  **Install dependencies:**
    Make sure you have Python 3.8+ installed. Then, install the required packages using pip:
    ```bash
    pip install langchain langchain-community langchain-huggingface chromadb pypdf langchain-openai
    ```

---

## ▶️ How to Run

1.  **Set up your LLM:**
    -   **For OpenAI**: Set your API key as an environment variable. In your terminal, run:
        ```bash
        export OPENAI_API_KEY="sk-..."
        ```
        *(On Windows Command Prompt, use `set OPENAI_API_KEY="sk-..."`)*
    -   **For Ollama (Local)**: Ensure the Ollama service is running and you have pulled a model (e.g., `ollama pull llama3`).

2.  **Update the script:**
    -   In `app.py`, change `"data/my_document.pdf"` to the name of your PDF file.
    -   Make sure the LLM initializer in the script matches your setup (e.g., `ChatOpenAI` or `ChatOllama`).

3.  **Execute the script:**
    Run the main application from your terminal:
    ```bash
    python app.py
    ```
    The script will process the document and print the answer to the hardcoded question.

---

## 📝 To-Do / Future Improvements

-   [ ] Create a web interface using Streamlit or FastAPI.
-   [ ] Allow users to input questions dynamically.
-   [ ] Add support for more document types (e.g., `.txt`, `.docx`).
-   [ ] Experiment with different embedding models and LLMs.