# Retrieval Augmented Generation (RAG) Chatbot for Hospital

Build a RAG chatbot agent in LangChain that uses Neo4j to based on OpenAI API/LLM and retrieved hospital sample data(including patients, patient experiences, hospital locations, visits, insurance payers, and physicians).

## Project Setup

Create a `.env` file in the root directory and add the following environment variables:

```.env
OPENAI_API_KEY=...

NEO4J_URI=...
NEO4J_USERNAME=...
NEO4J_PASSWORD=...

HOSPITALS_CSV_PATH=...
PAYERS_CSV_PATH=...
PHYSICIANS_CSV_PATH=...
PATIENTS_CSV_PATH=...
VISITS_CSV_PATH=...
REVIEWS_CSV_PATH=...

HOSPITAL_AGENT_MODEL=gpt-3.5-turbo-1106
HOSPITAL_CYPHER_MODEL=gpt-3.5-turbo-1106
HOSPITAL_QA_MODEL=gpt-3.5-turbo-0125

CHATBOT_URL=http://host.docker.internal:8000/hospital-rag-agent
```

The three `NEO4J_` variables are used to connect to your Neo4j AuraDB instance. Follow the directions [here](https://neo4j.com/cloud/platform/aura-graph-database/?ref=docs-nav-get-started) to create a free instance.

When you have a running Neo4j instance, and have filled out all the environment variables in `.env`, you can run the entire project with [Docker Compose](https://docs.docker.com/compose/). You can install Docker Compose by following [these directions](https://docs.docker.com/compose/install/).

After you've filled in all of the environment variables, set up a Neo4j AuraDB instance, and installed Docker Compose, open a terminal and run:

```console
$ docker-compose up --build
```

After each container finishes building, you'll be able to access the chatbot API at `http://localhost:8000/docs` and the Streamlit app at `http://localhost:8501/`.
