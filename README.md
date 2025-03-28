# Automated-Project Deployment-using-Shell-Scripting

## Overview
This project automates the process of detecting, building, and deploying different types of projects. It consists of multiple shell scripts that handle various tasks such as identifying the project type, managing builds, deploying the project, and cleaning up old backups.

## Prerequisites
Before using this automation, ensure you have the following installed on your system:
- **Git**: For pulling the latest code
- **Python**: If deploying a Python project
- **Java & Maven**: If deploying a Java project
- **Node.js & npm**: If deploying a Node.js project

## Repository Setup
1. **Clone the Repository:**
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```

2. **Make Scripts Executable:**
   ```bash
   chmod +x *.sh
   ```

## Scripts Explanation

### 1️⃣ `git_manager.sh`
Handles fetching the latest code from the repository.
```bash
./git_manager.sh
```
- Pulls the latest changes from the GitHub repository.
- Logs all actions in `logs/deploy.log`.

### 2️⃣ `build_manager.sh`
Identifies the project type and runs the necessary build commands.
```bash
./build_manager.sh
```
- Detects the type of project (HTML, Python, Java, or Node.js).
- Installs dependencies and builds the project accordingly.

### 3️⃣ `deploy_manager.sh`
Deploys the built project to the target environment.
```bash
./deploy_manager.sh
```
- Moves the necessary files to the deployment directory.
- Starts or restarts the server if required.

### 4️⃣ `cleanup_manager.sh`
Removes old backup files to free up space.
```bash
./cleanup_manager.sh
```
- Keeps only the latest 10 backups and deletes older ones.
- Ensures efficient storage management.

## Deployment Steps
1. **Pull the latest changes:**
   ```bash
   ./git_manager.sh
   ```
2. **Detect and build the project:**
   ```bash
   ./build_manager.sh
   ```
3. **Deploy the project:**
   ```bash
   ./deploy_manager.sh
   ```
4. **Clean up old backups (optional but recommended):**
   ```bash
   ./cleanup_manager.sh
   ```

## Logs & Debugging
- All script logs are stored in `logs/deploy.log` for reference.
- If any script fails, check the logs for error messages.

## Conclusion
This automated setup ensures a smooth and efficient project deployment process by handling everything from code updates to deployment and maintenance. 🚀
