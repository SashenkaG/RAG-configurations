A(["Begin"]):::startNode
B["Fetch from AWS S3"]:::processNode
C["Document Chunking"]:::processNode
D["Embedding Generation"]:::processNode
E["Data Ingestion"]:::processNode
F["Store in Pinecone"]:::processNode
G(["Complete"]):::endNode

A --> B --> C --> D --> E --> F --> G