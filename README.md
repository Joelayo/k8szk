# Introduction 
This project aims to provide a Docker image for running Zookeeper. Zookeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services.

# Getting Started
To get this code up and running on your own system, follow these steps:

1. **Installation process**:
   - Clone the repository: `git clone <repository-url>`
   - Navigate to the project directory: `cd <project-directory>`

2. **Software dependencies**:
   - Docker: Ensure Docker is installed and running on your system.
   - Azure CLI: Install the Azure CLI tool to interact with Azure services.

3. **API references**:
   - Refer to the official Zookeeper documentation for API references and usage.

# Build and Test
To build and push the new Zookeeper image to Azure Container Registry (ACR), follow these steps:

1. **Login to Azure**:
   - Open a terminal and login to your Azure account using the command:
     ```sh
     az login
     ```

2. **Set the ACR name**:
   - Set the name of your Azure Container Registry:
     ```sh
     ACR_NAME=<your-acr-name>
     ```

3. **Build and push the Docker image**:
   - Use the `az acr build` command to build and push the Docker image to ACR:
     ```sh
     az acr build --registry $ACR_NAME --image solr-zookeeper:latest .
     ```
   - This command will:
     - Build the Docker image using the Dockerfile in the current directory.
     - Tag the image as `solr-zookeeper:latest`.
     - Push the image to the specified ACR.

4. **Verify the image**:
   - After the build process completes, verify that the image has been pushed to ACR by listing the images:
     ```sh
     az acr repository list --name $ACR_NAME --output table
     ```