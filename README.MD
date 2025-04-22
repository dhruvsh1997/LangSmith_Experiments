# 🤖 Evaluating a RAG Chatbot with LangSmith

[![LangChain](https://img.shields.io/badge/LangChain-FF6C00?style=for-the-badge&logo=langchain&logoColor=white)](https://www.langchain.com/)
[![LangSmith](https://img.shields.io/badge/LangSmith-00B8D9?style=for-the-badge&logoColor=white)](https://smith.langchain.com/)
[![Groq](https://img.shields.io/badge/Groq-536DFE?style=for-the-badge&logoColor=white)](https://groq.com/)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/)

This notebook demonstrates the evaluation of a **Retrieval Augmented Generation (RAG)** chatbot using LangSmith. The chatbot is built using LangChain and leverages a PDF document as its knowledge base. LangSmith is used to create an evaluation dataset, define evaluation metrics, and execute the evaluations. The results are then visualized within the LangSmith platform.

## 📑 Key Components

### 1️⃣ Document Loading and Processing
- PDF document loading
- Text chunking for optimal retrieval
- Embeddings generation with Hugging Face
- FAISS vector store creation for efficient similarity search

### 2️⃣ LLM Setup
- Integration with ChatGroq LLM
- Parameter configuration for optimal performance
- API setup and authentication

### 3️⃣ Prompt Engineering
- Implementation of LangSmith Hub prompt templates
- Context-aware instruction design
- Optimization for retrieval-based responses

### 4️⃣ RAG Chain Creation
- LangChain retrieval QA chain implementation
- Integration of LLM, vector store and prompt template
- Configuration for effective knowledge retrieval

### 5️⃣ Evaluation Dataset Creation
- Test question definition and curation
- RAG chain execution for response generation
- Comprehensive logging in LangSmith including:
  - Generated responses
  - Retrieved source documents
  - Query processing metadata

### 6️⃣ Evaluation Metrics
- Accuracy evaluation using secondary Groq LLM
- Conceptual similarity assessment between:
  - Generated answers
  - Reference outputs from evaluation dataset

### 7️⃣ Evaluation Execution
- Automated evaluation using `client.evaluate()`
- Batch processing of test questions
- Comprehensive performance metrics collection

### 8️⃣ Results Visualization
- Interactive LangSmith dashboard
- Overall accuracy score visualization
- Detailed individual run analysis
- Performance diagnostics and insights

## 🛠️ Setup

1. **Library Installation**
```python
!pip install langchain langsmith groq faiss-cpu PyPDF2 huggingface_hub sentence_transformers
```

2. **Environment Variables**
```python
import os
os.environ["LANGSMITH_API_KEY"] = "your_langsmith_api_key"
os.environ["LANGSMITH_ENDPOINT"] = "https://api.smith.langchain.com"
os.environ["LANGSMITH_PROJECT"] = "rag-chatbot-evaluation"
os.environ["GROQ_API_KEY"] = "your_groq_api_key"
```

3. **PDF Document**
- Place your `testPDF.pdf` in the Colab environment
- The document serves as the knowledge base for the RAG system

## 🚀 Usage

1. **Run the Notebook**
   - Execute all cells sequentially
   - Monitor the evaluation process in real-time

2. **Evaluate Results**
   - Access the LangSmith platform using the provided link
   - Analyze accuracy scores and performance metrics
   - Review individual question responses

3. **Iterate and Improve**
   - Modify evaluation datasets
   - Adjust evaluation metrics
   - Refine prompts for better performance

## 🔮 Further Development

This notebook serves as a foundation for RAG chatbot evaluation. Potential expansions include:

- **Advanced Metrics**: Implement context relevance, hallucination detection, and response coherence metrics
- **Dataset Expansion**: Create more diverse and challenging evaluation questions
- **Model Experimentation**: Test different LLMs and embedding models for comparison
- **Parameter Tuning**: Optimize RAG chain settings and LLM parameters
- **UI Development**: Create an interactive interface for real-time querying
- **Multi-Document Support**: Extend the system to handle multiple knowledge sources

---

📝 **Note**: This evaluation framework provides quantitative insights into your RAG system's performance, enabling data-driven improvements to your chatbot's accuracy and reliability.