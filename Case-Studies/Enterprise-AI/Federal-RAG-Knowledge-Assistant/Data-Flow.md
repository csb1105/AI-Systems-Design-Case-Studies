# Data Flow

## Overview
The Federal RAG Knowledge Assistant uses a retrieval-first data flow. User questions are not answered directly by the language model alone. Instead, the system retrieves relevant approved documents, uses those documents as grounding context, and returns a response with source attribution.

## Primary Data Flow
1. An authorized user submits a natural language query through the web interface.
2. The request is routed through the API Gateway.
3. Authentication and role-based access controls verify the user's identity and permissions.
4. The Query Orchestrator receives the validated request.
5. The query is preprocessed for normalization, filtering, and retrieval preparation.
6. The Embedding Service converts the query into a vector representation.
7. The Vector Database performs similarity search against approved document embeddings.
8. The Retrieval Engine applies metadata filters such as role, office, document type, date, and sensitivity level.
9. Relevant document chunks are returned to the Query Orchestrator.
10. The Prompt Builder combines the user query, retrieved context, and response instructions.
11. The Large Language Model generates a grounded response using the retrieved source material.
12. The Citation and Attribution Layer attaches source references to the response.
13. The grounded answer is returned to the user.
14. Audit logs capture the query, retrieval results, generated response, citations, and system actions.

## Document Ingestion Flow
1. Approved documents are added through the Document Management Console.
2. The Document Ingestion Pipeline collects and validates the documents.
3. Documents are parsed into machine-readable text.
4. Content is chunked into smaller retrievable units.
5. Metadata is applied to each chunk.
6. Embeddings are generated for each chunk.
7. Document chunks, embeddings, and metadata are stored in the Vector Database.
8. Version control and freshness checks track document updates over time.

## Data Stores
* Vector Database
* Document Repository
* Metadata Store
* Audit Log Store
* User Access Control Records

## Data Flow Controls
* Role-based access control
* Metadata filtering
* Source attribution
* Document version tracking
* Audit logging
* Human review for high-risk outputs

## Output

The final output is a source-grounded response that includes citations or references to the approved documents used to generate the answer.
