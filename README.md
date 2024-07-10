# RAG Chatbot with LangChain and Neo4j

This project creates a Retrieval-Augmented Generation (RAG) chatbot using LangChain and Neo4j, specifically tailored for a large hospital system. The chatbot leverages them and uses OpenAI models to retrieve and generate contextually relevant responses.

## Project Overview

The code is structured into several directories, each serving a distinct purpose:
* data/: Contains raw hospital system data stored as CSV files. This data is explored and then moved into a Neo4j database.
* hospital_neo4j_etl/: Contains a script to load raw data from data/ into the Neo4j database. This script is crucial for preparing the database before building the chatbot.
* chatbot_api/: The FastAPI app that serves the chatbot as a REST endpoint. This is the core of the project. The chatbot_api/src/agents/ and chatbot_api/src/chains/ subdirectories contain the LangChain objects that make up the chatbot.
* tests/: Includes scripts to test how quickly the chatbot can answer questions, highlighting the efficiency of asynchronous requests to LLM providers like OpenAI.
* chatbot_frontend/: The Streamlit app that interacts with the chatbot endpoint in chatbot_api/. This is the user interface for the chatbot.

All environment variables needed to build and run the chatbot are stored in a .env file. A sample env file is included in the root directory. The code in hospital_neo4j_etl/, chatbot_api, and chatbot_frontend is deployed as Docker containers, orchestrated with Docker Compose.

## How I Built This Project

1. Learning LangChain:
I started by getting familiar with LangChain and setting up the initial environment. This included understanding the basics of LangChain and preparing the necessary tools.

2. Data Exploration:

I explored the hospital system data stored in CSV files in the data/ directory. This step involved understanding the structure and content of the data to effectively move it into a Neo4j database.

3. Setting up Neo4j:

I loaded the data into a Neo4j database and set up the Neo4j instance. This involved creating scripts to automate the data loading process and configuring the Neo4j environment.

4. Building the FastAPI App:

I developed the chatbot API using FastAPI and LangChain. This API serves as the core of the project, providing a REST endpoint for the chatbot. The chatbot is composed of LangChain agents and chains, which are configured in the chatbot_api/src/agents/ and chatbot_api/src/chains/ directories.

5. Creating the Frontend:

I built a Streamlit app in the chatbot_frontend/ directory to interact with the chatbot API. This app serves as the user interface for the chatbot, allowing users to interact with the system and get responses.

## Project build

To build and run the project, clone the repo, create the API keys and Neo4j store and create a env file in the root directory with the configured values.
To run the project, type in the terminal:

```
docker-compose up --build
```  
