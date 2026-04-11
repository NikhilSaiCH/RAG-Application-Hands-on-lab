# Exercise 3: Configure Azure AI Search for RAG

## Lab scenario

In this exercise, you will configure Azure AI Search to create a retrieval-augmented generation (RAG) pipeline. This service will index the documents from Azure Blob Storage, vectorize the content using the embedding model deployed in Exercise 2, and enable semantic search capabilities. By the end of this exercise, you will have a fully functional search index that can retrieve relevant documents for your AI applications.

## Lab objectives

In this exercise, you will complete the following tasks:

- Task 1: Navigate to Azure AI Search service
- Task 2: Configure data source connection to Azure Blob Storage
- Task 3: Set up vector embeddings using Azure OpenAI
- Task 4: Configure AI skills and advanced settings
- Task 5: Create and run the search index
- Task 6: Validate document indexing and search functionality

## Estimated time: 1 hour
## Task 1: Navigate to Azure AI Search Service
Start by locating and opening your Azure AI Search service in the Azure Portal.

1. In the Azure Portal search bar at the top, search for **"AI Search (1)"**
2. Select **AI Search service (2)** from the search results

![Navigate to AI Search](../Media/34.PNG)

3. Once the service opens, locate and click the **"Import data"** button in the Overview tab.

This action will launch the guided import wizard to configure your data pipeline.

![Open Import Data Wizard](../Media/35.PNG)

---
## Task 2: Configure Data Source Connection

1. On the "Choose a data source" screen, select **"Azure Blob Storage"**.

![Choose Data Source](../Media/36.PNG)

2. On the "What scenario are you targeting?" screen, select **"RAG"**.

![Select RAG Scenario](../Media/37.PNG)

---
## Task 3: Connect to Azure Blob Storage
Configure the connection details to your storage account where the documents are located.

1. In the "Configure your Azure Blob Storage" section, fill in the following fields:
   - **Subscription (1)**: Select your Azure subscription
   - **Storage account (2)**: Select your storage account name
   - **Blob container (3)**: Select blob container name (ex : content)
   - Leave **Blob folder** empty (unless documents are in a subfolder)
   - **Parsing mode**: Keep as "Default"
   - Click **"Next (4)"** to proceed

![Configure Blob Storage](../Media/38(a).PNG)

---
## Task 4: Set Up Vector Embeddings
Configure the Azure OpenAI embedding model to vectorize your document content for semantic search.

1. In the "Vectorize your text" section, configure:
   - **Kind (1)**: Select "Azure OpenAI"
   - **Subscription(2)**: Select your Azure subscription
   - **Azure OpenAI service (3)**: Select "cog" (your Azure OpenAI resource)
   - **Model deployment (4)**: Select "embedding" (the text-embedding-ada-002 model deployed in Exercise 2)
   - **Authentication type (5)**: Keep "API key" selected (default)
   - Check the **acknowledgment box (6)** confirming additional costs for Azure OpenAI service usage
   - Click **"Next" (7)** to continue

![Configure Embeddings](../Media/39.PNG)

---
## Task 5: Configure AI Skills and Advanced Settings
Set up optional enrichment and advanced search capabilities.

1. On the "Vectorize and enrich your images" screen:
   - Uncheck "Vectorize images" (for this lab, we'll focus on text)
   - Uncheck "Extract text from images" (not required for this scenario)

2. Click **"Next"** to proceed

![Configure Enrichment](../Media/40.PNG)

On the "Advanced settings" screen:

1. Enable **"Enable semantic ranker" (1)** to improve search relevance using semantic understanding
2. Keep other settings at default values
3. Click **"Next" (2)** to proceed

![Advanced Settings](../Media/41.PNG)

---
## Task 6: Review Configuration and Create Index
Review your complete configuration before creating the search resources.

1. On the "Review your configuration" screen, you'll see:
   - **Objects name prefix (1)**: "rag-index"
   - **Vectorize your text**: Azure OpenAI service with "embedding" model
   - **Semantic ranker**: Enabled
   - **Indexer run schedule**: Once (on-demand)

2. Click **"Create" (2)** to deploy the search infrastructure

![Review Configuration](../Media/42(a).PNG)

The wizard will now create:
- **Index**: The search index structure
- **Data source**: Connection to Blob Storage
- **Skillset**: Processing pipeline with embeddings
- **Indexer**: Orchestrator that pulls and processes documents

Wait for the success message displayed below and click **Close**

![Creation Success](../Media/43.PNG)

---
## Task 7: Monitor Data Source
Verify that the data source and indexer have been created successfully.

1. In the left sidebar, expand **"Search management" (1)** → **"Data sources" (2)**
2. You should see the data source listed, connected to your Azure Blob Storage **Click (3)** on it.

![Data Sources Created](../Media/44.PNG)

You can explore the Data Source configurations here.

![Data Source Details](../Media/45(a).PNG)

---
## Task 8: Check Indexer Status
Verify that the indexer has been created and is ready to run.

1. In the left sidebar, navigate **"Indexers" (1)**
2. You should a "Success" status indicator and click on the **Indexer (2)**

![Indexer Status](../Media/46.PNG)

Execute the indexer to process and index all documents from Blob Storage.

3. Click the **"Run" (3)** button to start indexing your documents

![Run Indexer](../Media/47.PNG)

A confirmation dialog will appear:

4. Click **"Yes" (4)** to confirm running the indexer

![Confirm Indexer Run](../Media/48.PNG)

The indexer will now crawl your Blob Storage, process each document, generate vector embeddings using the Azure OpenAI embedding model, and populate the search index.

---
## Task 9: Validate Index and Search
Verify that documents have been successfully indexed and are searchable.

1. In the left sidebar, navigate to **"Indexes" (1)**
2. Click on the **index name (2)** to view its details

![View Indexes](../Media/49.PNG)

3. The index overview shows:
   - Navigate to **Search explorer (3)**

4. Click **"Search" (4)** to retrieve results

![Search Explorer Results](../Media/50.PNG)

The search results display.
## Summary

In this exercise, you have accomplished the following:

- Navigated to the Azure AI Search service in the Azure portal
- Configured a data source connection to Azure Blob Storage for document ingestion
- Set up vector embeddings using the Azure OpenAI text-embedding-ada-002 model
- Configured AI skills and enabled semantic ranking for improved search relevance
- Created and deployed a search index with the import wizard
- Executed the indexer to process and index documents from Blob Storage
- Validated the search index functionality using the Search explorer

You have successfully completed Exercise 3 and created a fully functional Azure AI Search index that integrates with Azure OpenAI for semantic search capabilities. This RAG pipeline will be used in the next exercise to power intelligent document retrieval for the web application.

For additional information, refer to the [Azure AI Search documentation](https://learn.microsoft.com/azure/search/).