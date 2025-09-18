# Legal-ai-assistant



# ⚖️ AI-Powered Legal Document Analysis Assistant

This project is a  web-based tool designed to help lawyers, paralegals, and legal professionals analyze dense legal documents with the power of AI. It functions as a Retrieval-Augmented Generation (RAG) system, allowing users to upload contracts, case files, or statutes and perform a deep, interactive analysis.


![Business page](/legal-homepage.png)
---

## ✨ Key Features

* **Interactive Q&A**: Ask specific questions about your documents (e.g., "Find all clauses related to termination") and receive a synthesized summary backed by the exact, verbatim clauses from the source text.
* **AI-Suggested Questions**: Don't know where to start? The app uses the Gemini API to analyze your documents and suggests insightful, investigative questions to guide your analysis.
* **Contextual Term Definitions**: After an analysis, the assistant can extract key legal terms from the relevant clauses and provide definitions based *only* on the context of your documents, avoiding generic or irrelevant information.
* **Secure and Private**: All document processing and text chunking happens directly in your browser. The contents of your files are not stored on any server. Only the relevant text snippets are sent to the API for analysis.
* **Simple Local Setup**: The entire application is self-contained and can be run locally with a simple Python web server, ensuring your data remains on your machine.
* **Modern Interface**: A clean, professional, and easy-to-use interface built with Tailwind CSS.

---

## ⚙️ How It Works

The application uses a modern RAG pipeline combined with advanced features of the Gemini API.

1.  **Client-Side Processing**: When you upload documents, the JavaScript in your browser reads the files and splits them into logical chunks (paragraphs). This ensures your full documents never leave your computer.
2.  **Core RAG Analysis**:
    * **Retrieval**: When you ask a question, the app performs a keyword search on the client-side to find the most relevant text chunks.
    * **Augmentation**: These relevant chunks are combined with your question into a detailed prompt for the AI.
    * **Generation**: The prompt is sent to the Gemini API, which generates a summary and extracts the precise clauses as instructed.
3.  **Advanced Gemini Features**:
    * **Suggesting Questions**: A sample of the document text is sent to the Gemini API with a prompt asking it to act as a senior paralegal and return a JSON object containing a list of potential questions.
    * **Defining Terms**: The extracted clauses from the main analysis are sent to the Gemini API with a prompt asking it to identify key terms and return a JSON object containing the terms and their contextual definitions.

---

## 🛠️ Technology Stack

* **Frontend**: HTML, Tailwind CSS, Vanilla JavaScript
* **AI Model**: Google Gemini API (`gemini-2.5-flash-preview-05-20`) with JSON Mode for structured outputs.
* **Local Server**: Python 3, Flask

---

## 🚀 How to Run Locally

Follow these steps to get the application running on your own computer.

### Prerequisites

* Python 3.6 or newer installed on your system.

### Step 1: Set Up Project Files

1.  Create a main project folder named `legal-ai-assistant`.
2.  Inside it, create the exact folder structure and files as shown below.

### Step 2: Install Dependencies in a Virtual Environment

It is highly recommended to use a virtual environment.

1.  Open your terminal or command prompt and navigate into the `legal-rag-app` directory.
    ```bash
    cd legal-rag-app
    ```
2.  Create and activate the virtual environment:

    * **On macOS / Linux:**
        ```bash
        python3 -m venv venv
        source venv/bin/activate
        ```
    * **On Windows:**
        ```bash
        python -m venv venv
        .\venv\Scripts\activate
        ```
3.  Install the necessary package using pip:
    ```bash
    pip install -r requirements.txt
    ```

### Step 3: Run the Web Server

1.  With your virtual environment still active, run the Flask server:
    ```bash
    python server.py
    ```
2.  The terminal will show that the server is running and provide a local URL.
    ```
    Starting the RAG Citation App server...
    Open your browser and navigate to [http://127.0.0.1:5001](http://127.0.0.1:5001)
     * Running on [http://127.0.0.1:5001](http://127.0.0.1:5001)
    ```

### Step 4: Use the Application

1.  Open your web browser.
2.  Navigate to the address: **http://127.0.0.1:5001**

The Legal Document Analysis Assistant is now ready to use on your local machine.
