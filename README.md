ChemAgent: A Local-First AI Tutor for AP Chemistry 🧪
ChemAgent is an advanced, agentic AI tutor designed to provide comprehensive, personalized support for students preparing for the AP Chemistry exam. It runs entirely on your local machine, ensuring privacy and offline functionality.

This project uses a Retrieval-Augmented Generation (RAG) architecture with a Neo4j graph database to create a knowledgeable and interactive study partner.

## Core Features
Conceptual Explanations: Get clear, detailed explanations for complex topics like VSEPR theory, Le Chatelier's Principle, and thermodynamics.

Step-by-Step Problem Solving: Ask for help with quantitative problems (e.g., stoichiometry, equilibrium calculations) and get a full walkthrough.

100% Local and Private: All processing, from the AI model to the knowledge base, happens on your machine. Nothing is sent to the cloud.

Graph-Based Knowledge: Information is stored in a Neo4j knowledge graph, allowing the agent to understand and explain the relationships between different chemical concepts.

## Tech Stack & Architecture
ChemAgent is built with a modern, local-first AI stack:

Python: The core programming language.

LangChain: The framework for building the agentic application and connecting components.

Ollama: Serves the local Large Language Model (e.g., Llama 3 8B) that powers the agent's reasoning.

Neo4j: The graph database that acts as the agent's long-term memory and knowledge base.

The system uses a Master Control Program (MCP) design where a primary agent analyzes user queries and delegates tasks to specialized tools, such as the ChemistryKnowledgeBase tool for querying the graph.

## Setup and Installation
Follow these steps to get ChemAgent running on your local machine.

### 1. Prerequisites
Make sure you have the following software installed:

Ollama: Download and install from ollama.com.

Neo4j Desktop: Download and install from neo4j.com.

Once installed, create a new local database, start it, and install the APOC plugin from the "Plugins" tab.

### 2. Project Setup
Clone the Repository:

git clone https://github.com/your-username/chemagent.git
cd chemagent
Install Python Dependencies: Create a requirements.txt file with the following content:

langchain
langchain-ollama
langchain-neo4j
ollama
neo4j
Then, install the packages:

python3 -m pip install -r requirements.txt
Pull the LLM: Download the Llama 3 8B model via Ollama.

ollama pull llama3:8b
## Usage
Running the agent is a two-step process. First, you must populate the knowledge base. Then, you can run the interactive agent.

### Step 1: Populate the Knowledge Base
The agent's knowledge comes from the data you load into Neo4j. Run the ingestion script to add data from your source files (e.g., text from the OpenStax textbook).

python3 load_data.py
(You only need to do this when you want to add new information to the database.)

### Step 2: Run the ChemAgent Tutor
Start the main application to begin chatting with your AI tutor. Make sure Ollama and your Neo4j database are running before you start.

python3 chem_agent.py
The script will launch, and you can start asking AP Chemistry questions in your terminal. Type exit to quit.
