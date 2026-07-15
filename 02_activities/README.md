# Fossil Finder: An AI Assistant

Fossil Finder is designed to be a chatbot assistant that gives you information on fossils and dinosaurs. The assistant is designed as a museum curator that provides engaging explanations while using external tools to retrieve specialized information.

Fossil Finder uses Python, OpenAI, ChromaDB, and Gradio.

---

# Features and services

###
# Service 1: Literature Search (API Service)

This service retrieves information from OpenAlex API. You can ask questions about scientific literature.
The API response is processed by the language model and rewritten into a natural language summary.

###
# Service 2: Fossil Knowledge Search (Semantic Search)

This service uses retrieval-augmented generation (RAG) to answer questions using a local fossil database.

The embedded database is created separately and stored locally.

###
# Service 3: Dinosaur Information Tool (Function Calling)

The chatbot uses OpenAI function calling to access structured information. When asked something about a dinosaur age, it calls 'dinosaur_age'.
The function returns structured information about the dinosaur's geological period, which is then incorporated into the final response.

### User interface

The chatbot interface was implemented using Gradio.
The assistant has a defined personality:

"Fossil Finder is an enthusiastic museum curator who helps users learn about
prehistoric life."

Conversation history is maintained throughout interactions using Gradio's
conversation history.

## Guardrails

The chatbot includes restrictions to prevent:

- Revealing the system prompt
- Modifying system instructions
- Answering questions about:
  - cats
  - dogs
  - Taylor Swift
  - astrology/zodiac signs

Restricted queries return a predefined refusal response.

## Design Decisions

### Dataset

The semantic search database contains fossil and dinosaur information.
Documents were selected to provide concise factual descriptions suitable for
retrieval.

### Simplification

The project prioritizes reliability and modularity over complexity. Each
service was implemented independently and connected through the chat router.

### Memory Management

Conversation memory is maintained during the active session. Long-term memory
was not implemented because it was not required for the assignment.

---

## Running the Application

1. Install the course environment requirements.
2. Ensure OpenAI API credentials are configured.
3. Run the notebook/application.
4. Launch the Gradio interface.