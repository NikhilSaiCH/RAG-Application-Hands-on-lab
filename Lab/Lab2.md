# Exercise 2: Deploy Azure OpenAI Models and Upload Knowledge Base Documents

## Lab scenario

In this exercise, you will deploy the required Azure OpenAI model deployments for the RAG application and upload your knowledge base documents to Azure Blob Storage. You will create two model deployments—**GPT-4o** for chat completion and **text-embedding-ada-002** for embeddings—and then populate a Blob Storage container with the Contoso Real Estate sample documents.

## Lab objectives

In this exercise, you will complete the following tasks:

- Task 1: Navigate to Azure OpenAI Foundry portal
- Task 2: Deploy the GPT-4o model for chat completions
- Task 3: Deploy the text-embedding-ada-002 model for semantic embeddings
- Task 4: Navigate to Azure Blob Storage
- Task 5: Upload sample documents to the knowledge base

## Estimated time: 1 hour


## Task 1: Navigate to Azure OpenAI in the Azure Portal

1. From the Azure desktop, open the **Azure Portal**.

![Open Azure Portal](../Media/16.PNG)

2. In the search bar at the top, type **OpenAI (1)** and select **Azure OpenAI (2)**.

![Search for Azure OpenAI](../Media/17.PNG)

3. After the Azure OpenAI resource opens. From the top menu, click **Go to Foundry portal (1)**.

![Go to Foundry portal](../Media/18.PNG)

---

## Task 2: Deploy the GPT-4o Model

1. In the Foundry portal, navigate to **Model catalog (1)** from the left sidebar.

2. Search for **gpt-4o (2)** in the search box.

3. Select the **gpt-4o (3)** model and click **Use this model**.

![Search for GPT-4o model](../Media/19.PNG)


![Select GPT-4o model](../Media/20.PNG)

4. The deployment form opens. Click on **Customise** and configure the following settings:

   - **Deployment name (1):** `chat`
   - **Deployment type (2):** Select `Global Standard`
   - **Model version (3):** Select the Default Version.
   - **Tokens per Minute Rate Limit (4):** Keep at default (250K TPM) or adjust as needed
   - Review the deployment details and click **Deploy (5)**.

![Configure GPT-4o deployment](../Media/21.PNG)

![Review and deploy GPT-4o](../Media/22.PNG)

5. Wait for the model deployment to complete and proceed for the next step.

---

## Task 3: Deploy the text-embedding-ada-002 Model

1. In the Foundry portal, return to **Model catalog (1)**.

2. Search for **text-embedding-ada-002 (2)** in the search box.

3. Select the **text-embedding-ada-002 (3)** model and click **Use this model**.

![Search for embedding model](../Media/23.PNG)


![Select embedding model](../Media/24.PNG)

4. The deployment form opens. Click on **Customise** and configure the following settings:

   - **Deployment name (1):** `embedding`
   - **Deployment type (2):** Select `Global Standard`
   - **Model version (3):** Select the Default Version.
   - **Tokens per Minute Rate Limit (4):** Keep at default (250K TPM) or adjust as needed
   - Review the deployment details and click **Deploy (5)**.

![Configure embedding deployment](../Media/25.PNG)

![Review and deploy embedding model](../Media/26.PNG)

5. Wait for the deployment to complete.

---

## Task 4: Navigate to Azure Blob Storage

1. Return to the Azure Portal.

2. Search for **storage** in the search bar and select **Storage accounts (1)**.

![Search for Storage Accounts](../Media/27.PNG)

3. Click on the **storage account(1)** to open it.

![Open storage account](../Media/28.PNG)

4. In the left sidebar, expand **Data storage (1)** and click **Containers(2)**.

5. You will see two containers: `slogs` and `content`. Click on the **content (3)** container.

![Navigate to Containers](../Media/29.PNG)


---

## Task 5: Upload Documents to Blob Storage

1. Inside the content container, click the **Upload (1)** button.

2. In the upload panel on the right, click **Browse for files (2)** to select your Contoso Real Estate sample documents.

![Upload button in Blob Storage](../Media/30.PNG)

3. Navigate to the data folder  **`azure-labs\azure-search-openai-javascript\data`(1)** and select the **documents(2)** to upload (PDF or text files) and click **Open(3)**

   ![Select documents to upload](../Media/31.PNG)

4. Click **Upload (1)** to add the documents to the knowledge base.

   ![Upload documents](../Media/32.PNG)

   ![Upload confirmation](../Media/33.PNG)

---

## Summary

In this exercise, you have accomplished the following:

- Navigated to the Azure OpenAI Foundry portal through the Azure Portal
- Deployed the GPT-4o model for chat completions with the deployment name "chat"
- Deployed the text-embedding-ada-002 model for semantic embeddings with the deployment name "embedding"
- Located the Azure Blob Storage account and navigated to the content container
- Uploaded Contoso Real Estate sample documents to populate the knowledge base

You have successfully completed Exercise 2 and prepared the AI models and knowledge base documents needed for the RAG application in subsequent exercises.