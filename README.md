# Automated Project Deployment using Shell Scripting

## Overview
This project automates the process of detecting, building, and deploying different types of projects. It consists of multiple shell scripts that handle various tasks such as identifying the project type, managing builds, deploying the project, and cleaning up old backups.

## Prerequisites
Before using this automation, ensure you have the following installed on your system:

- **Git**: For pulling the latest code
- **Python**: If deploying a Python project
- **Java & Maven**: If deploying a Java project
- **Node.js & npm**: If deploying a Node.js project

## Repository Setup
### Clone the Repository
```bash
git clone <your-repo-url>
cd <your-repo-name>
```
### Make Scripts Executable
```bash
chmod +x *.sh
```

## Scripts Explanation

### 1️⃣ git_manager.sh
- Handles fetching the latest code from the repository.
- Run the script using:
  ```bash
  ./git_manager.sh 
  ```
- Pulls the latest changes from the GitHub repository.
- Logs all actions in `logs/deploy.log`.

### 2️⃣ build_manager.sh
- Identifies the project type and runs the necessary build commands.
- Run the script using:
  ```bash
  ./build_manager.sh
  ```
- Detects the type of project (**HTML, Python, Java, or Node.js**).
- Installs dependencies and builds the project accordingly.

### 3️⃣ deploy_manager.sh
- Deploys the built project to the target environment.
- Run the script using:
  ```bash
  ./deploy_manager.sh
  ```
- Moves the necessary files to the deployment directory.
- Starts or restarts the server if required.

### 4️⃣ cleanup_manager.sh
- Removes old backup files to free up space.
- Run the script using:
  ```bash
  ./cleanup_manager.sh
  ```
- Keeps only the latest **10 backups** and deletes older ones.
- Ensures efficient storage management.

## How to Run the Project

### Step 1: Run the Main Deployment Script
To start the deployment, execute the following command:
```bash
bash deploy/main_deploy.sh <gitrepo link>
```
Replace `<gitrepo link>` with the actual repository URL.

### Step 2: Run the Deploy Dashboard Script
Once the main deployment script has been executed, run the deploy dashboard script:
```bash
bash deploy/deploy_dashboard.sh
```

### Step 3: Check the Port Number
The dashboard runs on port **3000**. To access it, open Google Chrome (or any browser) and enter:
```
http://<your-ip-address>:3000
```
Replace `<your-ip-address>` with the actual IP address of your system.

### Step 4: Clean Up Old Backups (Optional but Recommended)
To manage storage efficiently, run:
```bash
./cleanup_manager.sh
```

## Logs & Debugging
- All script logs are stored in `logs/deploy.log` for reference.
- If any script fails, check the logs for error messages.

## Conclusion
This automated setup ensures a smooth and efficient project deployment process by handling everything from code updates to deployment and maintenance. 🚀
