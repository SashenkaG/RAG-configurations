A(["Begin"]):::startNode
B["Read from Google Drive"]:::processNode
C["Document Chunking"]:::processNode
D["Embedding Generation"]:::processNode
E["Data Ingestion"]:::processNode
F["Store in Weaviate"]:::processNode
G(["Complete"]):::endNode

A --> B --> C --> D --> E --> F --> G