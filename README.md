# Project Overview

This project is an application built using Langflow and Langchain, designed for analyzing data, creating vector databases (embeddings), processing user queries, and retrieving answers from databases in real-time. 
The application consists of several interconnected components in Langflow, including data ingestion, embedding generation, database search, and user interaction.

## System Requirements

To run the application locally, you need to have the following installed:

- Python 3.8+ (recommended version: 3.11+)
- Langflow (for creating the workflow)
- Langchain (for working with language models)
- Additionally, you will need an OpenAI account (to obtain an API key)
- Astra DB account (for storing and searching data).

## How to Run the Application

Run Langflow: After installing everything, run Langflow to create and execute your workflow.

In the terminal, navigate to the project folder and run:

`python langflow run`

## Project Structure

- File Input (for loading data)
- OpenAI Embeddings (for generating embeddings)
- Astra DB (for vector storage and search)
- Search Query (for querying the database)
- Data Processing and Text Parsing components for processing and preparing data for embedding.

Once the project is set up and running, you can use it to process data, generate embeddings, store them in Astra DB, and perform searches through the search query component. The results will be shown in real-time, allowing you to interact with the database directly.

