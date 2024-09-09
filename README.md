# Job Application Generator

This project generate a personalized application letter for a job position using various technologies. It involves extracting job details from a job description, querying a portfolio database for relevant projects, and creating a tailored application letter.

## Overview
1. Text Extraction and Processing:

- `ChatGroq`: Utilizes the Groq API to process and extract structured information from unstructured job descriptions.
- `PromptTemplate`: Helps in defining prompts for generating and parsing text from `str` type to `JSON` format.

2. Portfolio Management:
- `chromadb`: A vector database to store and query a collection of portfolio entries efficiently. And conduct similarity search.

3. Letter Generation:
- Uses the extracted job details and relevant project links to generate a personalized application letter.

## Components
1. Text Extraction
Technique: The `ChatGroq` model, which uses the `Llama-3.1-70b-versatile` version, is employed for extracting structured details from a job description.

Framework:

- `ChatGroq`: An advanced language model that can understand and generate human-like text. It is initialized with parameters such as the API key and temperature setting, which controls the randomness of the output.

Usage:

- PromptTemplate: Defines a template for generating extraction prompts. It instructs the model to extract specific details like `role`, `experience`, `skills`, and `description` from the input job description text.

- JsonOutputParser: Parses the output from the language model into a JSON format for easier handling and processing.
  
2. Portfolio Management
Technique: Utilizes `chromadb`, a vector database, to store and query a collection of portfolio entries based on their textual descriptions.

Framework:

- `chromadb`: An efficient database for storing and querying large sets of documents. It allows for semantic search by creating vector embeddings of text.

Usage:

- PersistentClient: Connects to the vector store and manages the portfolio collection.
- Document Addition and Querying: Adds documents to the collection and performs semantic queries to retrieve the most relevant portfolio entries based on the job description.

3. Email Generation
Technique: The script uses `ChatGroq` again to generate a customized application email by integrating the extracted job details and relevant portfolio links.

Framework:

- `PromptTemplate`: Defines the structure of the email generation prompt, ensuring that the email is tailored to the job description and includes links to relevant portfolio projects.

Usage:

Constructs a personalized application email that highlights the applicant's skills and portfolio projects in relation to the job requirements.


