# Expert Knowledge Worker
## A Question Answering Agent Powered by Retrieval-Augmented Generation (RAG)
This project implements a question answering agent that acts as an "expert knowledge worker." It's designed to provide highly accurate answers by leveraging Retrieval-Augmented Generation (RAG), which grounds its responses in a specific knowledge base.

The agent uses a conversational memory to maintain context throughout the chat and a visualizer to help you understand how the documents in the knowledge base are embedded.

## Features
RAG Pipeline: The core of the application uses a RAG pipeline to retrieve relevant document chunks from a vector store before generating a response with the LLM.

Persistent Vector Store: Documents are embedded using OpenAIEmbeddings and stored in a persistent Chroma vector database, so you don't need to re-embed the knowledge base on every run.

Conversational Memory: The ConversationBufferMemory from langchain allows the agent to remember the history of your conversation and provide more coherent and contextual answers.

Gradio UI: A simple, interactive chat interface is provided using the Gradio library, making it easy to interact with the agent.

Embedding Visualization: The notebook includes a dedicated section to visualize your document embeddings in a 2D space using t-SNE and Plotly, which can help you understand the relationships between documents.

## Requirements
Python 3.7+

OpenAI API Key: You'll need an OpenAI API key to access the gpt-4o-mini model and the embeddings model.

Knowledge Base: You must have a folder named knowledge_base in the same directory as the notebook. This folder should contain subdirectories for your different document types (e.g., products, solutions), with .md files inside them.

## Setup
Clone the repository: (If applicable)

git clone https://github.com/novaisDiogo/python_expert_knowledge_worker_RAG.git

## Install dependencies:
```bash
pip install openai langchain langchain-openai langchain-chroma python-dotenv gradio scikit-learn matplotlib plotly
```
## Set up your .env file:

Create a file named .env in the project's root directory and add your OpenAI API key.

OPENAI_API_KEY="your_api_key_here"

# Usage
Populate the knowledge base: Place your .md document files into categorized subfolders inside the knowledge_base directory (e.g., knowledge_base/products/product_info.md).

Run the notebook: Open the Jupyter Notebook and run all the cells. The notebook will automatically:

Load and split your documents.

Create a persistent Chroma vector database.

Launch the Gradio chat interface in your browser.

Chat with the agent: Use the chat interface to ask questions about the content in your knowledge base.

Visualize embeddings: Run the final cells of the notebook to generate an interactive 2D plot of your document embeddings.
