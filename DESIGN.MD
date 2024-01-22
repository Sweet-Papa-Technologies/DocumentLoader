# DocumentLoader

This is a docker application and suite of code to:
- Collect information from Jira, Gitlab, and Confluence
- Convert to vector data via LangChain tooling
- Store data into vector database
- Provide API to retrieve data from vector database

# Design and Setup:
[] Setup ChromaDB Docker and persistent storage
[] Setup App Docker Container
    [] Endpoint for Data Processing
    [] Endpoint for Data Retrieval

## Workflow Steps:

### 1) Collect Data
- Jira API -> Get all ticket data visible - Save to JSON Files
- Confluence API -> Get all document data visible -> Save to MD Files
- GitLab API - Get all visible repos -> Checkout main branch -> Save all code files to JSON Files

### 2) Convert Data to Vector
- Function to Convert Data to Vector with Metadata and Keywords

Document Loaders:
https://js.langchain.com/docs/modules/data_connection/document_loaders/ 
https://js.langchain.com/docs/modules/data_connection/document_loaders/json 

Document Splitters:
https://js.langchain.com/docs/modules/data_connection/document_transformers/character_text_splitter
https://js.langchain.com/docs/modules/data_connection/document_transformers/code_splitter

Embedding Generation:
https://js.langchain.com/docs/modules/data_connection/text_embedding/#embed_documents
https://js.langchain.com/docs/integrations/text_embedding/

### 3) Store Data Into Vector Database
- Write vector data to ChromaDB

https://js.langchain.com/docs/modules/data_connection/vectorstores/
https://js.langchain.com/docs/integrations/vectorstores 

### 4) Data Retrieval API
- Search ChromaDB for vector information
- Return string
