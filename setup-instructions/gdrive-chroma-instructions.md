
# Setup Instructions: Google Drive + Chroma

## What it does
This RAG ingestion integration automatically ingests files from Google Drive and generates embeddings, storing them in your Chroma vector database. These embeddings enable semantic search and retrieval for your RAG applications.

---

<details>
<summary><strong>Data Source Setup</strong></summary>

### Google Drive

- Get Google Drive API Key:
	- Go to [Google Cloud Console](https://console.cloud.google.com/)
	- Create a new project or select an existing one
	- Enable the Google Drive API
	- Generate a key as described in the [Google Documentation](https://docs.cloud.google.com/docs/authentication/api-keys#create)
- Get Folder ID:
	- Open your Google Drive folder in a browser
	- Copy the folder ID from the URL (after /folders/)
	- Example: https://drive.google.com/drive/folders/ABC123XYZ

</details>

---

<details>
<summary><strong>Vector Database Setup</strong></summary>

### Chroma

- Deploy Chroma:
	- Run Chroma server (Docker or standalone)
	- Note your Chroma host and port (default: localhost:8000)
- Collection Setup:
	- Define a collection name for your embeddings

</details>

---

<details>
<summary><strong>Embedding Model Setup</strong></summary>

### OpenAI

- Go to OpenAI platform and login to your account
- In the left sidebar, click on "API keys"
- Click the "Create secret key" button
- Copy the key and store it securely

### Mistral AI

- Go to Mistral AI console
- Go to the API Keys section from the left-hand navigation bar
- Copy it and store it securely

### Azure OpenAI

- Go to Azure OpenAI Service
- Go to the Keys and Endpoint section located in the left-hand navigation menu under "Resource Management"
- You will see two keys (KEY 1 and KEY 2). You can use either one. Copy the key and store it securely
- Base URL (Endpoint): The Endpoint URL will be displayed here, typically in the format https://<your-resource-name>.openai.azure.com/

</details>
