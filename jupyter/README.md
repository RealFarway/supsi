# Jupyter Notebook - Dockerized

A simple Docker Compose setup for running Jupyter Notebook with C and Python kernels in an isolated container environment.

## Overview

This Docker Compose configuration provides a clean, containerized Jupyter Notebook environment with automatic restart capabilities, ensuring your notebooks are always available when you need them.

### Key Features
- **Multi-kernel support**: Both C and Python kernels included
- **Persistent availability**: Containers automatically restart with your system
- **Clean host system**: All dependencies contained within Docker
- **IDE integration**: Full Visual Studio Code compatibility

## Prerequisites

- [Docker Engine](https://docs.docker.com/engine/) or [Docker Desktop](https://docs.docker.com/desktop/) installed on your system
- Basic familiarity with command line operations
- (Optional) Visual Studio Code for IDE integration

## Installation

### Step 1: Clone or Download the Repository
Ensure you have the `docker-compose.yaml` file in your local directory.

### Step 2: Configure Security Token
Before starting the container, customize your access token:

1. Open `docker-compose.yaml` in a text editor
2. Locate the line containing `JUPYTER_TOKEN=password`
3. Replace `password` with a secure token of your choice, or keep it like that since it will only run locally

    environment:
      - JUPYTER_TOKEN=your_secure_token_here

### Step 3: Start the Container
Navigate to the directory containing the docker-compose file and run:

    docker compose up -d

The `-d` flag runs the container in detached mode (background).

### Step 4: Access Jupyter Notebook
1. Open your web browser
2. Navigate to `http://localhost:8888`
3. Enter the token you configured in Step 2 when prompted

## Visual Studio Code Integration

Transform VS Code into a powerful Jupyter environment by connecting it to your Docker container.

### Setup Instructions

1. **Install the Jupyter Extension**
   - Open VS Code
   - Navigate to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
   - Search for and install the [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) by Microsoft

2. **Connect to the Docker Container**
   - Open any `.ipynb` file in VS Code
   - Attempt to run a code cell
   - When prompted for a kernel, select **"Existing Jupyter Server"**
   - Enter the server URL: `http://localhost:8888`
   - Provide your JUPYTER_TOKEN when requested

3. **Select Your Kernel**
   - For C notebooks: Select the **C kernel**
   - For Python notebooks: Select **Python 3**
   - You can switch kernels using the kernel selector in the top-right corner of the notebook interface

### Container won't start
- Ensure Docker is running: `docker --version`
- Check if port 8888 is already in use: `netstat -an | grep 8888`
- Review container logs: `docker compose logs`

### Can't connect from VS Code
- Verify the container is running: `docker ps`
- Confirm the correct URL: `http://localhost:8888` (not https)
- Double-check your token is entered correctly

### Kernel connection issues
- Restart the container: `docker compose restart`
- Clear VS Code's Jupyter cache and reconnect

## Benefits

✅ **Clean Environment**: Keep your host system free from Python/C dependencies  
✅ **Version Control**: Easy to share consistent environments across teams  
✅ **Quick Setup**: Get started in minutes with minimal configuration  
✅ **Persistence**: Auto-restart ensures notebooks are always available

### Special thanks

Thank you claude.ai for re-writing this guide :D