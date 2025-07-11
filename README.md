Project Overview
This project is an AI-powered Streamlit app that:

Takes a YouTube video link as input.

Extracts the video’s transcript using youtube-transcript-api.

Splits the transcript into chunks and creates vector embeddings using HuggingFaceEmbeddings.

Stores the embeddings in a FAISS vector store for semantic search.

Uses LangChain to retrieve the most relevant parts of the transcript based on a user’s question.

Uses Google Gemini (via google-generativeai) to generate an answer only from the retrieved context (RAG-style).

Displays the Gemini answer through a simple Streamlit interface.


Features
Fetches real YouTube video captions automatically.

Works with Hindi or English captions if available.

Uses modern RAG (Retrieval-Augmented Generation) design.

Answers only from the video’s actual transcript.

Easy to run locally on VSCode or any Python environment.



How It Works
User provides a YouTube video URL and a question.

The app extracts the captions for the video (using youtube-transcript-api).

The text is split into manageable chunks for embedding.

Each chunk is embedded using sentence-transformers/all-MiniLM-L6-v2.

All embeddings are stored in a FAISS index.

The user’s question is used to retrieve the top-k most relevant chunks.

These chunks form the context for a prompt to Gemini.

Gemini generates an answer only from this context.



