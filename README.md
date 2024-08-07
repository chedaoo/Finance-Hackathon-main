# Ask Finance

## Overview

Ask Finance is a Streamlit application that allows users to upload PDF files, process their contents, and ask questions related to finance. The application leverages LangChain, FAISS, and Google Generative AI to provide detailed and accurate responses. This application aims to solve the issue of missing out on important points in a long legal documents by the end user. This LLM is not only trained to fetch the data from the uploaded document but also make any suggestive response when prompted.

## Features

- **PDF Text Extraction:** Extracts text from uploaded PDF files.
- **Text Chunking:** Splits the extracted text into manageable chunks for processing.
- **Vector Store Creation:** Uses FAISS to create a vector store of the text chunks.
- **Conversational Chain:** Utilizes Google Generative AI to generate responses based on the provided context and questions.

## Installation

### Prerequisites

- Python 3.6+

### Setup

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/ask-finance.git
    cd ask-finance
    ```

2. **Install dependencies:**

    Create a `requirements.txt` file with the following content:

    ```plaintext
    streamlit
    google-generativeai
    python-dotenv
    langchain
    PyPDF2
    chromadb
    faiss-cpu
    langchain_google_genai
    langchain-community
    ```

    Then, install the dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. **Set up environment variables:**

    Create a `.env` file in the project root and add your Google API key:

    ```env
    GOOGLE_API_KEY=your_google_api_key
    ```

## Usage

1. **Run the application:**

    ```bash
    streamlit run app.py
    ```

2. **Upload PDF files:**

    - Use the sidebar menu to upload multiple PDF files.

3. **Process the PDFs:**

    - Click on the "Submit & Process" button to extract and process the text from the uploaded PDFs.

4. **Ask questions:**

    - Enter your financial question in the provided input box and receive detailed answers based on the processed PDF contents.

## Code Explanation

### Extract Text from PDFs

The `get_pdf_text` function extracts text from the uploaded PDF files using the PyPDF2 library.

### Text Chunking

The `get_text_chunks` function splits the extracted text into smaller chunks using LangChain's `RecursiveCharacterTextSplitter`.

### Vector Store Creation

The `get_vector_store` function creates a vector store from the text chunks using FAISS and Google Generative AI embeddings.

### Conversational Chain

The `get_conversational_chain` function sets up a conversational chain using Google Generative AI to generate responses based on the provided context and questions.

### User Input Handling

The `user_input` function handles user questions, searches for relevant text chunks, and generates responses using the conversational chain.

### Main Function

The `main` function sets up the Streamlit interface, handles PDF uploads, and processes user questions.

## Contributing

Contributions are welcome! Please fork the repository and submit pull requests for any features or bug fixes.

## License

This project is licensed under the MIT License.
