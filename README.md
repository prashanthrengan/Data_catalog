
# **Data Catalog with Vector Search and NLP**

## **Overview**

This Python script sets up a metadata catalog for an enterprise data warehouse using a combination of natural language processing (NLP) and vector search technologies. It leverages the `SentenceTransformer` model to generate semantic embeddings for metadata descriptions and uses Pinecone, a vector database, to enable efficient similarity searches.

## **Features**

- **Metadata Ingestion**: Load metadata from a CSV file into a Pandas DataFrame.
- **Embedding Generation**: Convert metadata descriptions into vector embeddings using the `SentenceTransformer` model.
- **Vector Search**: Store and query metadata embeddings with Pinecone to find relevant data based on user queries.
- **Interactive Chat Interface**: Allow users to interactively query the metadata catalog through a command-line interface.

## **Prerequisites**

- **Python 3.x**: Ensure you have Python 3.x installed.
- **Required Libraries**: The script requires the following libraries:
  - `pandas`
  - `sentence-transformers`
  - `pinecone-client`

## **Setup**

### **1. Install Required Libraries**

Install the necessary libraries using pip:

```bash
pip install pandas sentence-transformers pinecone-client
```

### **2. Prepare Metadata File**

Ensure you have a CSV file (`data_catalog.csv`) with the following columns:
- `table_name`
- `column_name`
- `description`

This file should be located in the same directory as the script or specify the path accordingly.

### **3. Configure Pinecone**

Replace the `api_key` placeholder with your actual Pinecone API key in the script:

```python
pc = Pinecone(api_key="your-api-key")
```

### **4. Set Up Pinecone Index**

The script creates or connects to an existing Pinecone index. Make sure the index configuration (e.g., dimension) matches the embeddings' size used by the `SentenceTransformer` model.

## **Usage**

### **1. Run the Script**

Execute the script in your Python environment:

```bash
python data_catalog.py
```

### **2. Interact with the Catalog**

Once the script is running, you can start interacting with the metadata catalog through the command-line interface:

- **Query**: Type your questions or keywords related to the metadata.
- **Exit**: Type `exit` to terminate the chat session.

### **Example Queries**

- "What is the description of the 'user_id' column in the 'users' table?"
- "Tell me about the 'email' field in the 'contacts' table."

## **Code Explanation**

- **Data Ingestion**: The script reads metadata from a CSV file into a Pandas DataFrame.
- **Embedding Generation**: Uses `SentenceTransformer` to convert text descriptions into vector embeddings.
- **Pinecone Integration**: Sets up a Pinecone index to store and query embeddings.
- **Query Function**: Converts user queries into embeddings, performs similarity search, and returns relevant metadata.

## **Troubleshooting**

- **Pinecone API Key Issues**: Ensure your API key is correct and has the necessary permissions.
- **Library Installation**: If you encounter installation issues, check for compatibility with your Python version and operating system.
- **Data Format**: Verify that the CSV file follows the required format and contains the necessary columns.

## **Future Enhancements**

- **Web Interface**: Develop a web-based interface for easier interaction.
- **Database Integration**: Transition metadata storage from CSV to a relational database like PostgreSQL.
- **Model Fine-Tuning**: Fine-tune the `SentenceTransformer` model on domain-specific data for improved accuracy.

## **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## **Acknowledgments**

- **SentenceTransformers**: For providing pre-trained models for generating embeddings.
- **Pinecone**: For offering a scalable vector database solution.



