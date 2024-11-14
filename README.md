# HelpMate AI - RAG System

## Project Overview

This project implements a **Retrieval-Augmented Generation (RAG)** system designed to answer questions based on insurance-related documents. Using **LlamaIndex** for document indexing and **OpenAI's GPT models** for response generation, the system offers contextually relevant answers to user queries.

## Features

- Document indexing with **LlamaIndex**.
- Context-aware response generation using **OpenAI's GPT**.
- Flexible query handling, including follow-up questions.
- Testing pipeline to evaluate response accuracy.

## Requirements

- Python 3.x
- LlamaIndex
- OpenAI
- Pandas
- Google Colab (optional)

## Installation

1. Install the necessary libraries:
   ```bash
   pip install llama-index openai pandas
Set up your OpenAI API key by creating a .txt file containing your key and storing it in the project directory.
How to Run
Load your documents (e.g., insurance FAQs) into a pandas DataFrame.
Use the LlamaIndex to index the documents and create the query engine.
Use OpenAI's GPT to generate responses based on user queries.
Test the system using predefined questions to evaluate accuracy.

from llama_index import SimpleIndex
import openai

# Initialize the index
index = SimpleIndex()

# Add documents to the index
for doc in insurance_documents:
    index.add_document(doc)

# Query Engine
query = "What are the coverage details for health insurance?"
response = index.query(query)

# Generate Response using OpenAI
openai_response = openai.Completion.create(
    engine="text-davinci-003",
    prompt=response,
    max_tokens=150
)
print(openai_response.choices[0].text.strip())
Future Improvements
Enhanced query handling for follow-up questions.
Use of customized nodes for better response generation.
Implement sub-question engines to improve query resolution.
