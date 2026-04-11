# Azure OpenAI + Azure AI Search Lab Guide

Welcome to the Azure OpenAI and Azure AI Search workshop. This repository contains a step-by-step lab guide for building a Retrieval-Augmented Generation (RAG) application using Azure services.

## Architecture Overview

The diagram below shows the complete RAG architecture used in this lab:

![Architecture Diagram](./Media/app-architecture.png)

The system includes:

- **Decoupled Frontend App**: Hosts the chat interface and sends user questions to the backend.
- **Search Node.js Service**: Orchestrates semantic search and Azure OpenAI completions.
- **Document Ingestion Node.js Service**: Uploads documents, creates embeddings, and indexes content.
- **Azure OpenAI Service**: Provides chat completions and embeddings.
- **Azure AI Search**: Performs semantic search using vector embeddings.
- **Azure Blob Storage**: Stores knowledge base documents.

## Lab Modules

This guide is organized into four exercises:

1. **Exercise 1: Environment Setup and Application Deployment**
   - Set up Visual Studio Code and required tools
   - Authenticate to Azure
   - Deploy backend and frontend code to pre-provisioned resources

2. **Exercise 2: Deploy Azure OpenAI Models and Upload Knowledge Base Documents**
   - Deploy GPT-4o and text-embedding-ada-002 models
   - Upload Contoso Real Estate documents to Azure Blob Storage

3. **Exercise 3: Configure Azure AI Search for RAG**
   - Configure Azure AI Search to index documents
   - Set up vector embeddings and semantic ranking
   - Create and run the indexer

4. **Exercise 4: Access and Test the Deployed RAG Web Application**
   - Locate and open the deployed Static Web App
   - Test the chat interface with enterprise queries
   - Validate the RAG workflow and response citations

## Getting Started

Open the `Lab` folder and follow the lab files in order:

- `Lab/Lab1.md`
- `Lab/Lab2.md`
- `Lab/Lab3.md`
- `Lab/Lab4.md`

Each lab file contains step-by-step instructions, screenshots, and validation guidance.

## Prerequisites

Before you begin, ensure you have:

- An Azure subscription with access to Azure OpenAI and Azure AI Search
- Visual Studio Code installed
- Azure Developer CLI (`azd`) installed
- Node.js LTS installed
- Docker desktop
- Git installed
- PowerShell installed

## Notes

- The lab assumes Azure resources are pre-provisioned.
- Exercise 1 focuses on deploying application code, not provisioning resources.
- Exercise 2 and Exercise 3 configure models, document ingestion, and search.
- Exercise 4 validates the final RAG web application.

## Repository Structure

```text
Lab_Guide/
  ├── Lab/
  │   ├── Lab1.md
  │   ├── Lab2.md
  │   ├── Lab3.md
  │   ├── Lab4.md
  │   └── Getting_Started.md
  ├── Media/
  │   ├── app-architecture.png
  │   └── ...screenshots...
  └── Readme.md
```

## Recommended Workflow

1. Start with `Lab/Lab1.md` to configure your environment and deploy the code.
2. Continue with `Lab/Lab2.md` to deploy models and upload documents.
3. Complete `Lab/Lab3.md` to configure search and indexing.
4. Finish with `Lab/Lab4.md` to test the application end-to-end.

Enjoy the lab and feel free to use the architecture diagram as your reference for the full RAG workflow.