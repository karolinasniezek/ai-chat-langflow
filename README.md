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

## How to Run the Langflow

Run Langflow: After installing everything, run Langflow to create and execute your workflow.

In the terminal, navigate to the project folder and run:

`python langflow run`

After installing the application and the required dependencies, you can launch Langflow. However, please note that by default, only an empty instance of Langflow is started, without the project I have created in Langflow.

## Project Structure

- File Input (for loading data)
- OpenAI Embeddings (for generating embeddings)
- Astra DB (for vector storage and search)
- Search Query (for querying the database)
- Data Processing and Text Parsing components for processing and preparing data for embedding.

Once the project is set up and running, you can use it to process data, generate embeddings, store them in Astra DB, and perform searches through the search query component. The results will be shown in real-time, allowing you to interact with the database directly.

# Chatbot Application with Langflow and Langchain

## Data Loading and Preparation

Components Used:
- `File Component`
- `Split Text`
- `OpenAI Embeddings`
- `Astra DB`

https://github.com/user-attachments/assets/8d829806-5ed9-4592-be63-1aac94a4325a


The first part of the workflow is concerned with loading the data and preparing it for further processing.

### File Component:

The first step of the process is to load the data file. In this case, a CSV file containing course data `Course Modules - Sheet1.csv` will be processed and analyzed.

### Split Text:

Once the data is loaded, it's split into manageable chunks (or "text blocks"). This allows for more efficient processing and ensures that the chatbot can analyze smaller portions of text at a time. 
The chunk size is adjustable, and for example, 1000 words per chunk is a typical setting. This approach makes it easier to process large files, especially when dealing with large-scale textual datasets.

### OpenAI Embeddings:

After splitting, each text chunk is passed through OpenAI’s embedding model `text-embedding-3-small`, which converts the text into numerical vectors (embeddings).
These embeddings represent the semantic meaning of the text, enabling the chatbot to search for similar queries or text later on.

### Astra DB

The embeddings are then stored in Astra DB, which serves as a scalable solution for storing and querying vectors. In this case, in this case a database called `langflow_db` is used to store the embeddings.

## Processing User Queries and Searching for Responses in the Database

Components Used:
- `Text Input`
- `OpenAI Embeddings`
- `Astra DB`
- `Data Message`

https://github.com/user-attachments/assets/12fc8a5e-541e-4457-a425-2848fa434fd2


### Text input

This component allows the user to input a query or text for analysis. In this case, the user asks the question "do you teach OOP?".

### OpenAI Embeddings

In this step, the user's input is transformed into a vector (embedding) using the OpenAI model `text-embedding-3-small`. Generating embeddings allows representing the text in numerical form, enabling later search and comparison of similar queries.

### Astra DB

The generated embeddings are stored in Astra DB, a scalable and powerful NoSQL database.
This storage setup enables the chatbot to efficiently retrieve embeddings and perform similarity searches, ensuring real-time access to data.
Data is stored in the `langflow_db` database.

### Data to Message 

Finally, the search results are converted into messages that can be displayed to the user. The `Data to Message` component transforms the resulting data into a message format, making it usable for display or further use in the application. 

## User Interaction and Response Generation

This section of the project handles the user's input and generates a response using OpenAI's GPT model. Here's a breakdown of the workflow:

Components Used:
- `Data to Message`
- `Prompt`
- `OpenAI`
- `Text Output`

https://github.com/user-attachments/assets/63ce04b3-214f-486f-b460-c839ee610d43


### Data to Message: 

Converts input data into a message format using a dynamic template. The data includes context, question, and website, which are formatted into a message for the next step.

### Prompt: 

Builds a dynamic prompt for OpenAI by inserting the user's data into predefined placeholders - in this case `{context}`, `{question}`). This creates a clear prompt for the AI.

### OpenAI: 

Sends the dynamically generated prompt to OpenAI's GPT-4 Mini model for processing. The model generates a response based on the prompt, and the temperature is set to 0.10 for more deterministic results.

### Text Output: 

Displays the AI-generated response, which is presented to the user.

This workflow enables efficient interaction with OpenAI models and generates real-time responses based on user input.

## Business Use Cases

The application I have built using Langflow and Langchain can be applied to a variety of business use cases where intelligent data analysis, real-time query handling, and customer interactions are needed.

### Automated Customer Support

The application can provide businesses with a 24/7 automated customer support solution. By integrating with the company’s database, the chatbot can respond to customer inquiries in real time regarding products, services, availability, pricing, and complaint procedures.

### Automated Information and Report Searching

This solution is ideal for businesses with large datasets - reports. The chatbot allows employees to quickly search for relevant information, using embeddings to return accurate results based on user queries.

### Personalized Education and Training

The application can be utilized in the education sector to create personalized learning programs and provide support to students. The chatbot can answer student queries, explain difficult concepts, and offer further learning suggestions based on past results.

### Market Data Analysis and Trend Prediction

The application can analyze market data and predict trends based on historical data. By processing information from various sources such as industry reports, articles, and social media, the chatbot can deliver real-time insights and forecasts about industry developments, price changes, or consumer trends.
