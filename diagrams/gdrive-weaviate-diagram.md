Start((Start))
ReadFrom["Read from Google Drive"]
Chunking{{"Document Chunking"}}
Embedding{{"Embedding Generation"}}
Ingestion{{"Data Ingestion"}}
StoreIn["Store in Weaviate"]
End((End))

Start --> ReadFrom
ReadFrom --> Chunking
Chunking --> Embedding
Embedding --> Ingestion
Ingestion --> StoreIn
StoreIn --> End