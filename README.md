# ThinkTank-Backend – Intelligent Document Analysis API

ThinkTank-Backend is the Flask-based backend powering the ThinkTank AI chatbot system. It handles document upload, processing, vector embedding, and intelligent responses using Azure's powerful AI services.

# Features

Secure PDF upload via Azure Blob Storage (SAS tokens)

Text extraction using Azure Document Intelligence

Real-time Q&A with Azure OpenAI (GPT-4o)

Indexed document search using Azure Cognitive Search

Stateless, session-based architecture with robust error handling

# Getting Started
Clone or download the repo:

git clone https://github.com/<your-org>/ThinkTank-Backend.git
Or download as ZIP and extract.

# Set up your environment:

cd ThinkTank-Backend
python -m venv venv
source venv/bin/activate      # macOS/Linux  
venv\Scripts\activate         # Windows
pip install -r requirements.txt

# Add Azure credentials:

# Create a .env file in the root with:

AZURE_OAI_ENDPOINT=
AZURE_OAI_KEY=
AZURE_OAI_DEPLOYMENT=

AZURE_DOCUMENT_INTELLIGENCE_ENDPOINT=
AZURE_DOCUMENT_INTELLIGENCE_KEY=

AZURE_BLOB_CONNECTION_STRING=
AZURE_BLOB_CONTAINER=
AZURE_BLOB_KEY=

AZURE_SEARCH_ENDPOINT=
AZURE_SEARCH_KEY=
AZURE_SEARCH_INDEX=


# Run the backend server:

python backend.py
Then open http://localhost:5000 to confirm it's running.

# API Endpoints
Endpoint	Description
POST /upload_and_ask	Upload document and ask a one-time question
POST /extract_text	Extract raw text from uploaded document
POST /followup_chat	Continue chat using previous document + history

# Security
Files stored temporarily with time-limited SAS tokens

No persistent data storage (stateless session handling)

User login and auth handled on frontend (Streamlit)
