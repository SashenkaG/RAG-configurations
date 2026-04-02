## What it does
This RAG ingestion integration automatically ingests files from Google Drive and generates embeddings, storing them in your Chroma vector database. These embeddings enable semantic search and retrieval for your RAG applications.

<details>
<summary><strong>Data Source Setup</strong></summary>

### Google Drive

#### Method 1: API Key (Recommended for simple setup)

- Get Google Drive API Key:
	- Go to [Google Cloud Console](https://console.cloud.google.com/)
	- Create a new project or select an existing one
	- Enable the Google Drive API
	- Generate a key as described in the [Google Documentation](https://docs.cloud.google.com/docs/authentication/api-keys#create)
- Get Folder ID:
	- Open your Google Drive folder in a browser
	- Copy the folder ID from the URL (after /folders/)
	- Example: https://drive.google.com/drive/folders/ABC123XYZ

#### Method 2: OAuth (Client Credentials) - Optional

Use this method if the API Key method doesn't work for your use case.

- Create OAuth 2.0 Credentials:
	- Go to [Google Cloud Console](https://console.cloud.google.com/)
	- Navigate to "Credentials" → "Create Credentials" → "OAuth 2.0 Client ID"
	- Select "Desktop application" and click "Create"
	- Download the credentials JSON file
	- Extract `client_id` and `client_secret`

- Get Refresh Token using curl:
	- Replace YOUR_CLIENT_ID and YOUR_CLIENT_SECRET with your actual values
	- Run the first curl command to get the authorization code:
	  `curl -X POST https://oauth2.googleapis.com/token -d "client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET&scope=https://www.googleapis.com/auth/drive&redirect_uri=http://localhost&response_type=code&access_type=offline"`
	- Follow the authorization link in the response and copy the authorization code
	- Run the second curl command with your authorization code:
	  `curl -X POST https://oauth2.googleapis.com/token -d "client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET&code=AUTHORIZATION_CODE&grant_type=authorization_code&redirect_uri=http://localhost"`
	- Copy the `refresh_token` from the response and store it securely

</details>

<details>
<summary><strong>Vector Database Setup</strong></summary>

### Chroma

- Deploy Chroma:
	- Run Chroma server (Docker or standalone)
	- Note your Chroma host and port (default: localhost:8000)
- Collection Setup:
	- Define a collection name for your embeddings

</details>

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
