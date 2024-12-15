## WikiNews Search Engine

### Overview
The **WikiNews Search Engine** is a comprehensive retrieval-augmented generation (RAG) system designed to combine Wikipedia knowledge with real-time news data to provide accurate and contextually relevant answers to user queries. The project uses machine learning and natural language processing (NLP) techniques to process, embed, and search through vast amounts of textual data.

---

### Features
1. **Knowledge Base Construction**:
   - Leverages the **Wikipedia 20220301.simple** dataset for general knowledge.
   - Incorporates real-time news articles fetched using the **NewsAPI** to provide up-to-date information.

2. **Document Chunking**:
   - Splits documents into manageable chunks using a **Recursive Character Text Splitter** adapted for the embedding model's maximum token length (256 tokens).

3. **Embeddings and Vector Storage**:
   - Generates embeddings for all chunks using **sentence-transformers/all-MiniLM-L6-v2**.
   - Stores embeddings in a **FAISS vector store** for efficient similarity search with cosine distance.

4. **Retrieval-Augmented Generation**:
   - Retrieves the most relevant documents for a given query.
   - Uses a **HuggingFace pipeline** with a lightweight language model for contextualized, natural language answers.

5. **2D Visualization**:
   - Projects high-dimensional embeddings into 2D using PCA and PaCMAP for visualization and exploratory analysis of document relevance.

6. **Query-Based Information Retrieval**:
   - Allows users to ask questions and receive concise, accurate answers.
   - Provides document metadata and sources for transparency and verifiability.

---

### Key Components
1. **Wikipedia Knowledge Base**:
   - Extracts and preprocesses data from Wikipedia.
   - Stores raw and chunked data in JSON files for reproducibility.

2. **NewsAPI Integration**:
   - Fetches real-time news articles related to the query.
   - Processes and embeds the news data alongside Wikipedia knowledge.

3. **FAISS Vector Search**:
   - Combines Wikipedia and NewsAPI embeddings into a unified vector database.
   - Retrieves relevant documents based on cosine similarity.

4. **HuggingFace Language Models**:
   - Employs **HuggingFaceH4/zephyr-7b-beta** with 4-bit quantization for fast and memory-efficient generation.
   - Generates answers in response to user queries, using retrieved documents as context.

5. **Visualization**:
   - Uses **PaCMAP** for 2D projections of embeddings to illustrate relationships between query vectors and document embeddings.
   - Displays visualizations via **Plotly**.

---

### Outputs
1. **Answer to Query**:
   - The system returns a concise and contextually accurate answer.
   - Includes the date and relevant metadata from source documents.

2. **Document Metadata**:
   - Lists the most relevant documents and their sources for reference.

3. **2D Visualization**:
   - Shows relationships between query and document embeddings in a scatter plot.

---

### Applications
- **Research**:
  - Quickly gather relevant information on a topic from trusted sources.
- **Real-Time Insights**:
  - Stay updated with current events while cross-referencing historical context.
- **Education**:
  - Use the system as a learning tool for retrieving accurate and concise information.

---

### Tools
This project leverages open-source datasets and tools, including:
- Hugging Face Transformers
- LangChain
- Sentence Transformers
- NewsAPI
- PaCMAP
