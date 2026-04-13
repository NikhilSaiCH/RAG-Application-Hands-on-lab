# Exercise 1: Environment Setup and Application Deployment

## Lab scenario

This exercise ensures your workshop environment is ready to begin the Azure OpenAI and Azure AI Search experience. You will launch Visual Studio Code, open the lab repository, authenticate with Azure, and deploy the application code to pre-provisioned Azure resources through the terminal.

## Lab objectives

In this exercise, you will complete the following tasks:

- Task 1: Launch Visual Studio Code and set up the development environment
- Task 2: Authenticate with Azure
- Task 3: Deploy application code to pre-provisioned resources

## Estimated time: 1 hour 15 minutes

## Task 1: Launch Visual Studio Code and Set Up Environment

### Launch Visual Studio Code

1. From the lab desktop, click the Visual Studio Code icon to open the editor.

   ![Open Visual Studio Code](../Media/10.PNG)

2. The VS Code Welcome page appears once the application starts. Click on **Open Folder(1)**.

   ![VS Code Welcome](../Media/11.PNG)

3. Search for **`azure-search-openai-javascript (1)`** folder and click **Select folder (2)**.

   ![Open Folder in VS Code](../Media/11(a).PNG)

4. Open a **new terminal** from the VS Code **Terminal** menu.

   ![Open a new terminal](../Media/12.PNG)

> Use the terminal at the bottom of VS Code to run commands.

### Navigate to Repository

Change into the lab repository directory:

**Run:**

```powershell
cd azure-search-openai-javascript
```

![](../Media/12(a).PNG)

### Install Required Tools and Prerequisites

Run the following commands to install and verify each required tool. If prompted, accept all license agreements and allow changes to your device.

#### Azure Developer CLI (azd)

```powershell
winget install microsoft.azd
azd version
```

![](../Media/12(b).PNG)

#### Node.js LTS

```powershell
winget install OpenJS.NodeJS.LTS
node -v
npm -v
```

![](../Media/12(c).PNG)

#### Git

```powershell
winget install Git.Git
git --version
```

![](../Media/12(e).PNG)

#### PowerShell

```powershell
winget install Microsoft.PowerShell
pwsh --version
```

![](../Media/12(f).PNG)

>Note: Docker is required for containerizing and deploying the application services via Azure Container Apps. It is preinstalled and running in the background on your lab environment—no manual installation or setup is needed. If you encounter issues, ensure Docker Desktop is active.

## Task 2: Authenticate with Azure

1. In the terminal, authenticate to Azure using the Azure Developer CLI:

   ```powershell
   azd auth login
   ```

2. The browser opens and prompts you to **sign in(1)** to Azure.

   ![Select your Azure account](../Media/13.PNG)

3. After a successful login, the browser confirms that authentication is complete.

   ![Authentication complete](../Media/14.PNG)

   Then to create an environment run the below command in the terminal:
    ```
    azd env new ragproject
    ```
    After the .env is created proceed to next step.

4. **Run:**

   ```
   az account show
   ```

   And copy the **subscription id (1)**

   ![](../Media/14(a).PNG)

5. **Run:**

   ```
   az group list --output table
   ```

   And copy the **resource group (1)**

   ![](../Media/14(b).PNG)

6. After coying the resource group paste the resource group in the below command between the braces and remove the braces later then run the command to get the latest deployed templates.

   ```
   az deployment group list --resource group () -o table
   ```

   ![](../Media/14(ba).PNG)

   scroll to bottom and copy the **Deployment Template(1)**

   ![](../Media/14(bb).PNG)

7. Then navigate to **setup-env.ps1(1)** and add the 3 values you copied at **resource group (2)**, **subscription id (3)** and **deployed name(4)** section and then save it (ctrl+S).

   ![](../Media/14(c).PNG)

   ![](../Media/14(db).PNG)

8. Then run:

   ```
   .\setup-env.ps1
   ```

   ![](../Media/14(e).PNG)

   this will setup the environment automatically.

## Task 3: Deploy Application Code

1. After the environment is set up you can then run:

   ```powershell
   azd deploy
   ```

   ![](../Media/14(f).PNG)

   Wait for up to 5-10 minutes for the deployment process to complete.

   > **azd deploy** in this exercise deploys the backend logic and frontend code to the pre-provisioned Azure Container Apps and Static Web App, ensuring all deployed components are connected and operational.

   ![Deployment progress showing the packaging and deployment of application services](../Media/14(g).PNG)

While the deployment is in progress, you can navigate to the Azure portal and explore all the pre-provisioned resources created for this lab. This will help you understand the Azure services that power your application.

### Navigate to Azure Portal and View Resources

1. Navigate to the [Azure portal](https://portal.azure.com).

   ![Azure portal home page](../Media/16.PNG)

2. In the Azure portal, search for **Resource groups(1)** in the search bar at the top.

3. Click on **Resource groups(2)** from the search results.

4. Locate and click on your **lab's resource group(3)**.

5. Once inside the resource group, you'll see an overview of all the Azure resources that have been pre-provisioned for this lab.

   ![Resource groups page showing the lab's resource group](../Media/14(i).PNG)

   ![Resource group overview displaying all deployed Azure services](../Media/14(j).PNG)

6. Take a moment to explore the different resources. You can click on individual resources to view their configurations and settings.

   ![Detailed view of Azure Container App and other key resources](../Media/14(k).PNG)

> **Note**: Familiarizing yourself with these resources will be helpful as you work through subsequent exercises where you'll interact with Azure OpenAI, Azure AI Search, and other services.

### Resources Created

The following Azure resources have been pre-provisioned for this lab:

| Resource | Description |
|----------|-------------|
| Application Insights | Monitors application performance, detects anomalies, and provides insights for troubleshooting and optimization. |
| Container Apps Environment | Provides the underlying infrastructure for running containerized applications with automatic scaling and management. |
| Azure OpenAI | Hosts OpenAI models for natural language processing, text generation, and AI-powered features in the application. |
| Container Registry | Stores Docker container images used for deploying the backend services. |
| Shared Dashboard | Provides a centralized view of resource metrics and health status across the Azure environment. |
| Smart Detector Alert Rule | Automatically detects and alerts on potential issues in application performance and resource usage. |
| Search Service | Powers the search functionality, enabling efficient querying and indexing of data within the application. |
| Managed Identity | Provides secure authentication for Azure resources without storing credentials in code. |
| Log Analytics Workspace | Collects and analyzes logs from all Azure resources for monitoring and troubleshooting. |
| Container App | Runs the backend application logic in a serverless container environment. |
| Storage Account | Provides scalable cloud storage for application data, blobs, and static content. |
| Static Web App | Hosts the frontend user interface with global distribution and automatic scaling. |

## Summary

In this exercise, you have accomplished the following:

- Set up the development environment with Visual Studio Code and required tools
- Authenticated with Azure and configured the environment
- Deployed application code to pre-provisioned Azure resources
- Reviewed the Azure resources created for the lab environment

You have successfully completed Exercise 1 and are ready to proceed with the next exercises.


