[04/11, 09:14] Parth Xie: https://github.com/rubenlagus/TelegramBots
[04/11, 09:14] Parth Xie: https://github.com/bonigarcia/selenium-jupiter.git
Here’s a **complete step-by-step guide** to perform **various Git operations** on **local and remote repositories**, suitable for your **AWS + Ubuntu + Jenkins lab setup** 👇

---

## 🔧 **Experiment 9: Perform Various Git Operations on Local and Remote Repositories**

### **Objective:**

To understand and perform various Git operations like initialization, commit, push, pull, clone, branch creation, and merge between local and remote repositories.

---

## 🖥️ **Setup Requirements**

* AWS EC2 instance with **Ubuntu** (for Git operations)
* Git installed (`sudo apt install git -y`)
* GitHub account (for remote repository)
* Jenkins (optional, if integration is needed later)

---

## ⚙️ **Step-by-Step Procedure**

### **1. Configure Git**

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

👉 *This sets up your Git identity used in commits.*

---

### **2. Create a Local Repository**

```bash
mkdir git-demo
cd git-demo
git init
```

Output:

```
Initialized empty Git repository in /home/ubuntu/git-demo/.git/
```

---

### **3. Add Files and Commit**

```bash
echo "Hello Git" > hello.txt
git add hello.txt
git commit -m "Initial commit"
```

Check status:

```bash
git status
```

---

### **4. Create a Remote Repository on GitHub**

* Go to GitHub → Click **New Repository** → Name: `git-demo`
* Do **not** initialize with a README (we already have one locally)

Copy the remote URL, e.g.:

```
https://github.com/username/git-demo.git
```

---

### **5. Link Local Repo with Remote**

```bash
git remote add origin https://github.com/username/git-demo.git
```

Verify:

```bash
git remote -v
```

---

### **6. Push Code to Remote Repository**

```bash
git branch -M main
git push -u origin main
```

After this, check GitHub — your file should appear.

---

### **7. Clone Remote Repository (on another system or folder)**

```bash
cd ~
git clone https://github.com/username/git-demo.git
```

---

### **8. Create a New Branch**

```bash
cd git-demo
git checkout -b feature1
```

Add new file and commit:

```bash
echo "New feature added" > feature.txt
git add feature.txt
git commit -m "Added new feature file"
```

Push branch to remote:

```bash
git push -u origin feature1
```

---

### **9. Merge Branch into Main**

Switch to main branch:

```bash
git checkout main
```

Merge:

```bash
git merge feature1
```

Push changes:

```bash
git push origin main
```

---

### **10. Pull Latest Changes from Remote**

```bash
git pull origin main
```

---

### **11. Delete a Branch**

```bash
git branch -d feature1        # delete locally
git push origin --delete feature1  # delete remotely
```

---

## 📄 **Result:**

Successfully performed local and remote Git operations such as:

* Initialization (`git init`)
* Adding and committing files
* Creating and merging branches
* Pushing and pulling from a remote repository

---

## 🧠 **Conclusion:**

Git efficiently manages version control between local and remote repositories. Developers can track changes, collaborate, and manage versions seamlessly using Git commands.

---
Here’s the **complete step-by-step guide** for your **Experiment 10: Pull Ubuntu image in Docker and execute bash** — exactly as needed for your AWS + Ubuntu lab setup 👇

---

## 🧪 **Experiment 10: Pull Ubuntu Image in Docker and Execute Bash**

### **Objective:**

To learn how to pull an Ubuntu image from Docker Hub, create and run a container, and execute commands using Bash inside the container.

---

## 🖥️ **System Requirements**

* AWS EC2 Instance (Ubuntu)
* Docker installed and running

---

## ⚙️ **Step-by-Step Procedure**

### **1. Update System Packages**

```bash
sudo apt update -y
```

---

### **2. Install Docker (if not installed)**

```bash
sudo apt install docker.io -y
```

Enable and start Docker service:

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

Check Docker version:

```bash
docker --version
```

---

### **3. Verify Docker Installation**

```bash
sudo docker run hello-world
```

✅ *If you see a "Hello from Docker!" message, installation is successful.*

---

### **4. Pull Ubuntu Image from Docker Hub**

```bash
sudo docker pull ubuntu
```

Output (sample):

```
Using default tag: latest
latest: Pulling from library/ubuntu
Digest: sha256:...
Status: Downloaded newer image for ubuntu:latest
```

---

### **5. Verify the Pulled Image**

```bash
sudo docker images
```

Output example:

```
REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
ubuntu       latest    47b19964fb50   2 weeks ago    77.8MB
```

---

### **6. Run Ubuntu Container in Interactive Bash Mode**

```bash
sudo docker run -it ubuntu /bin/bash
```

Now you are inside the container (prompt changes to something like this):

```
root@b8f5cdd1e5c3:/#
```

You can now execute Linux commands inside the container.

Example:

```bash
ls
pwd
cat /etc/os-release
```

---

### **7. Exit the Container**

Type:

```bash
exit
```

This stops and exits the running container.

---

### **8. View All Containers**

List all containers (running and stopped):

```bash
sudo docker ps -a
```

---

### **9. Start a Stopped Container**

```bash
sudo docker start -ai <container_id>
```

---

### **10. Remove Containers and Images (Optional Cleanup)**

Remove a container:

```bash
sudo docker rm <container_id>
```

Remove the Ubuntu image:

```bash
sudo docker rmi ubuntu
```

---

## 🧾 **Result:**

Successfully pulled the **Ubuntu Docker image**, created a **container**, and executed **bash** inside it to run Linux commands.

---

## 🧠 **Conclusion:**

This experiment demonstrates the use of Docker to pull and run Ubuntu containers. Docker provides an isolated environment where multiple OS instances can run independently on the same host.

---

Would you like me to generate this experiment as a **formatted PDF report (with commands + expected output + screenshots placeholders)** for your AWS practical submission?


Would you like me to include **screenshots commands** (for GitHub + Ubuntu terminal) in a **formatted PDF report** for submission? I can create it next.
Here’s the **complete step-by-step guide** for your **Experiment 11: Pull files from GitHub using Git, make changes, and push files back to GitHub** — fully written in a **practical + report format** (perfect for AWS Ubuntu lab submission). 👇

---

## 🧪 **Experiment 11: Pull Files from GitHub Using Git, Make Changes, and Push File to GitHub**

### **Objective:**

To understand how to pull a project from a remote GitHub repository, modify files locally, and push the updated files back to GitHub using Git commands.

---

## 🖥️ **System Requirements**

* AWS EC2 Instance with **Ubuntu**
* **Git** installed (`sudo apt install git -y`)
* A valid **GitHub account**
* Internet connectivity

---

## ⚙️ **Step-by-Step Procedure**

### **1. Configure Git (if not already done)**

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

Check configuration:

```bash
git config --list
```

---

### **2. Clone (Pull) Repository from GitHub**

Go to GitHub → copy the repository’s HTTPS link, e.g.:

```
https://github.com/username/sample-repo.git
```

Now, clone it into your AWS Ubuntu system:

```bash
git clone https://github.com/username/sample-repo.git
```

Move into the repository folder:

```bash
cd sample-repo
```

---

### **3. Verify the Pulled Files**

```bash
ls
```

You’ll see the list of files from the GitHub repository.

---

### **4. Create or Modify a File**

Let’s modify or create a new file:

```bash
echo "This is an update from AWS Ubuntu" >> update.txt
```

You can verify the file contents:

```bash
cat update.txt
```

---

### **5. Check Repository Status**

```bash
git status
```

Output example:

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	update.txt
```

---

### **6. Add the File to the Staging Area**

```bash
git add update.txt
```

---

### **7. Commit the Changes**

```bash
git commit -m "Added update.txt file with AWS note"
```

Output example:

```
[main 1a2b3c4] Added update.txt file with AWS note
 1 file changed, 1 insertion(+)
 create mode 100644 update.txt
```

---

### **8. Push Changes Back to GitHub**

```bash
git push origin main
```

If prompted for authentication:

* Enter your **GitHub username**
* Enter your **personal access token** (instead of password)

---

### **9. Verify Changes on GitHub**

Go to your GitHub repository page → refresh it.
You’ll see the newly updated/added file (`update.txt`) in the main branch.

---

### **10. Pull Changes (If Any New Commits Are Made Remotely)**

If someone else has updated the repository, pull the latest changes:

```bash
git pull origin main
```

---

## 🧾 **Result:**

Successfully pulled the repository from GitHub, made modifications locally, and pushed the updated files back to GitHub.

---

## 🧠 **Conclusion:**

This experiment demonstrates the complete Git workflow — cloning, editing, committing, and pushing — showing how developers collaborate efficiently using version control in distributed environments like AWS.

---

Would you like me to create this experiment as a **formatted PDF report** (with command outputs + screenshot placeholders) for submission? I can generate it right away.
Here’s the **complete and exam-ready practical write-up** for your **Experiment 12: Pull, List, and Remove Docker Images** — formatted for your AWS + Ubuntu lab report 👇

---

## 🧪 **Experiment 12: Pull Docker Images, List the Docker Images Currently Stored on Your Machine, and Remove an Image You No Longer Need**

### **Objective:**

To understand how to pull Docker images from Docker Hub, view the list of available images on the local system, and remove unnecessary images using Docker commands.

---

## 🖥️ **System Requirements**

* AWS EC2 Instance with **Ubuntu**
* **Docker** installed and running

---

## ⚙️ **Step-by-Step Procedure**

### **1. Update System Packages**

```bash
sudo apt update -y
```

---

### **2. Install Docker (if not already installed)**

```bash
sudo apt install docker.io -y
```

Enable and start Docker:

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

Verify Docker version:

```bash
docker --version
```

---

### **3. Pull Docker Images**

You can pull any image from **Docker Hub**.
For example, pull **Ubuntu** and **Nginx** images:

```bash
sudo docker pull ubuntu
sudo docker pull nginx
```

Output example:

```
Using default tag: latest
latest: Pulling from library/ubuntu
Digest: sha256:...
Status: Downloaded newer image for ubuntu:latest
```

---

### **4. List Docker Images Stored Locally**

```bash
sudo docker images
```

Sample output:

```
REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
nginx        latest    605c77e624dd   2 weeks ago    142MB
ubuntu       latest    47b19964fb50   2 weeks ago     77MB
```

✅ This command displays:

* Repository name
* Tag (version)
* Image ID
* Created date
* Image size

---

### **5. Remove an Unused Docker Image**

If you no longer need an image, remove it using its **Image ID** or **name**:

Example using name:

```bash
sudo docker rmi nginx
```

Or using Image ID:

```bash
sudo docker rmi 605c77e624dd
```

Output:

```
Untagged: nginx:latest
Deleted: sha256:605c77e624dd...
```

---

### **6. Verify Image Removal**

```bash
sudo docker images
```

You’ll now see that the **nginx** image has been removed from your list.

---

## 🧾 **Result:**

Successfully pulled Docker images from Docker Hub, listed the locally stored images, and removed an unwanted image from the system.

---

## 🧠 **Conclusion:**

This experiment demonstrates the management of Docker images — downloading, listing, and cleaning up — which helps in maintaining an efficient container environment and conserving disk space.

---

Would you like me to create a **formatted PDF version** of this experiment (with command outputs, explanations, and screenshot placeholders) for your practical submission?
Here’s the **complete and report-ready practical write-up** for your **Experiment 13: Execute Basic Commands in Docker and CMD** — written in a clear, step-by-step format suitable for your **AWS + Ubuntu lab submission** 👇

---

## 🧪 **Experiment 13: Execute Basic Commands in Docker and with CMD**

### **Objective:**

To learn and execute basic Docker commands in Ubuntu (Linux terminal) and CMD (Windows command prompt) for managing containers, images, and system information.

---

## 🖥️ **System Requirements**

* **AWS EC2 instance (Ubuntu)** with Docker installed
* **Windows system** with Docker Desktop and Command Prompt (CMD)

---

## ⚙️ **Step-by-Step Procedure**

---

### 🧩 **Part A: Execute Basic Docker Commands (on Ubuntu)**

#### **1. Check Docker Version**

```bash
docker --version
```

✅ Displays the installed Docker version.

---

#### **2. Display Docker System Information**

```bash
sudo docker info
```

✅ Shows details about Docker installation, number of containers, images, and storage driver.

---

#### **3. List All Docker Images**

```bash
sudo docker images
```

✅ Displays all images available locally.

---

#### **4. List Running Containers**

```bash
sudo docker ps
```

To view all (running + stopped) containers:

```bash
sudo docker ps -a
```

---

#### **5. Pull an Image from Docker Hub**

```bash
sudo docker pull ubuntu
```

---

#### **6. Run a Container in Interactive Mode**

```bash
sudo docker run -it ubuntu /bin/bash
```

✅ Starts an Ubuntu container and opens a bash shell.

You can run basic Linux commands inside the container:

```bash
ls
pwd
cat /etc/os-release
```

Exit container:

```bash
exit
```

---

#### **7. Start and Stop Containers**

List containers:

```bash
sudo docker ps -a
```

Start a container:

```bash
sudo docker start <container_id>
```

Stop a running container:

```bash
sudo docker stop <container_id>
```

---

#### **8. Remove Unused Containers or Images**

Remove container:

```bash
sudo docker rm <container_id>
```

Remove image:

```bash
sudo docker rmi <image_id>
```

---

#### **9. Check Docker Disk Usage**

```bash
sudo docker system df
```

---

#### **10. Remove All Unused Data (Clean-up)**

```bash
sudo docker system prune -f
```

✅ Deletes unused images, containers, and networks.

---

### 💻 **Part B: Execute Basic Commands in CMD (Windows Command Prompt)**

> 💡 Make sure Docker Desktop is installed and running before executing commands.

#### **1. Check Docker Version**

```cmd
docker --version
```

---

#### **2. Check System Information**

```cmd
docker info
```

---

#### **3. List Docker Images**

```cmd
docker images
```

---

#### **4. List Running Containers**

```cmd
docker ps
```

---

#### **5. Run an Ubuntu Container**

```cmd
docker run -it ubuntu
```

This will open an interactive bash shell inside the Ubuntu container.

---

#### **6. Stop and Remove Containers**

```cmd
docker stop <container_id>
docker rm <container_id>
```

---

#### **7. Remove Unused Images**

```cmd
docker rmi <image_id>
```

---

#### **8. View Docker Help**

```cmd
docker --help
```

✅ Displays all available Docker commands and their usage.

---

## 🧾 **Result:**

Successfully executed basic Docker commands using both **Ubuntu terminal** and **Windows CMD**, including listing images, managing containers, and viewing Docker system information.

---

## 🧠 **Conclusion:**

This experiment demonstrates the fundamental Docker commands used in Linux (Ubuntu) and Windows (CMD) environments. It helps in managing images, containers, and system configurations efficiently — essential skills for DevOps and cloud-based workflows.

---

Would you like me to create a **formatted PDF lab report** (with outputs, explanations, and screenshot placeholders) for this experiment too?

Here’s the **complete practical write-up** for your **Experiment 14: Execute Basic Commands in Git** — formatted perfectly for your **AWS Ubuntu lab submission or practical report** 👇

---

## 🧪 **Experiment 14: Execute Basic Commands in Git**

### **Objective:**

To understand and execute the basic Git commands used for initializing a repository, tracking files, committing changes, and synchronizing with remote repositories.

---

## 🖥️ **System Requirements**

* AWS EC2 Instance (Ubuntu)
* **Git** installed (`sudo apt install git -y`)
* Active **GitHub account** (for remote operations)

---

## ⚙️ **Step-by-Step Procedure**

---

### **1. Check Git Installation**

```bash
git --version
```

✅ Displays the installed version of Git.
Example Output:

```
git version 2.34.1
```

---

### **2. Configure Git User Information**

Set your name and email (these details appear in commits):

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

To verify configuration:

```bash
git config --list
```

---

### **3. Initialize a New Git Repository**

Create a project folder:

```bash
mkdir git-demo
cd git-demo
```

Initialize Git inside it:

```bash
git init
```

✅ Creates a hidden `.git` directory for version control.

---

### **4. Create a New File**

```bash
echo "Hello Git" > hello.txt
```

Check file:

```bash
cat hello.txt
```

---

### **5. Check Repository Status**

```bash
git status
```

✅ Shows tracked/untracked files and pending commits.

---

### **6. Add File to Staging Area**

```bash
git add hello.txt
```

To add all files at once:

```bash
git add .
```

---

### **7. Commit Changes**

```bash
git commit -m "Initial commit: added hello.txt"
```

✅ Commits the file to local repository history.

---

### **8. View Commit History**

```bash
git log
```

✅ Displays commit details (author, date, message).

---

### **9. Create a Branch**

```bash
git branch feature
```

Switch to that branch:

```bash
git checkout feature
```

---

### **10. Merge Branch into Main**

Switch back to main:

```bash
git checkout main
```

Merge:

```bash
git merge feature
```

---

### **11. Connect to Remote Repository**

Create a new repository on **GitHub**, then link it to your local repo:

```bash
git remote add origin https://github.com/username/git-demo.git
```

Verify:

```bash
git remote -v
```

---

### **12. Push Local Commits to Remote Repository**

```bash
git branch -M main
git push -u origin main
```

---

### **13. Pull Updates from Remote Repository**

```bash
git pull origin main
```

✅ Fetches and merges latest changes from GitHub.

---

### **14. Clone an Existing Repository**

```bash
git clone https://github.com/username/sample-repo.git
```

---

### **15. View All Branches**

```bash
git branch
```

---

### **16. Delete a Branch**

```bash
git branch -d feature
```

---

## 🧾 **Result:**

Successfully executed basic Git commands including repository creation, file tracking, committing, branching, merging, and pushing to a remote GitHub repository.

---

## 🧠 **Conclusion:**

This experiment familiarizes users with fundamental Git commands essential for version control and collaboration. Git helps developers efficiently manage code history, track changes, and synchronize work across multiple systems.

---

Would you like me to create this experiment as a **formatted PDF report** (with command outputs, explanations, and screenshot placeholders) for your AWS/Git practical submission?
Here’s the **complete and submission-ready write-up** for your **Experiment 15: Create a Git repository, add a new file, commit, and push to remote** — perfectly formatted for your **AWS + Ubuntu lab report** 👇

---

## 🧪 **Experiment 15: Create a Git Repository, Add a New File to the Repository, Commit the Changes with a Meaningful Message, and Push the Changes to a Remote Repository**

### **Objective:**

To learn how to create a new Git repository, add and commit files locally, and push the changes to a remote repository hosted on GitHub.

---

## 🖥️ **System Requirements**

* AWS EC2 instance running **Ubuntu**
* **Git** installed (`sudo apt install git -y`)
* Active **GitHub account** for remote repository access

---

## ⚙️ **Step-by-Step Procedure**

---

### **1. Configure Git (if not already configured)**

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

Check configuration:

```bash
git config --list
```

---

### **2. Create a New Project Directory**

```bash
mkdir my-first-repo
cd my-first-repo
```

---

### **3. Initialize Git Repository**

```bash
git init
```

✅ Output:

```
Initialized empty Git repository in /home/ubuntu/my-first-repo/.git/
```

This command creates a new Git repository in the current directory.

---

### **4. Create a New File**

```bash
echo "This is my first Git repository." > readme.txt
```

Check the file contents:

```bash
cat readme.txt
```

---

### **5. Check the Current Status**

```bash
git status
```

✅ Shows that `readme.txt` is an untracked file.

---

### **6. Add the File to the Staging Area**

```bash
git add readme.txt
```

Or add all files at once:

```bash
git add .
```

---

### **7. Commit the Changes with a Meaningful Message**

```bash
git commit -m "Added readme.txt file describing project purpose"
```

✅ Output:

```
[main (root-commit) abc1234] Added readme.txt file describing project purpose
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

---

### **8. Create a Remote Repository on GitHub**

1. Go to [GitHub](https://github.com) → Click **New Repository**
2. Name it **my-first-repo**
3. Do **not** initialize it with a README (since we already have one)
4. Copy the repository URL (e.g.):

   ```
   https://github.com/username/my-first-repo.git
   ```

---

### **9. Link Local Repository with Remote**

```bash
git remote add origin https://github.com/username/my-first-repo.git
```

Verify remote link:

```bash
git remote -v
```

✅ Output:

```
origin  https://github.com/username/my-first-repo.git (fetch)
origin  https://github.com/username/my-first-repo.git (push)
```

---

### **10. Push Changes to the Remote Repository**

Rename branch to `main` (if not already):

```bash
git branch -M main
```

Push changes:

```bash
git push -u origin main
```

When prompted, enter your:

* GitHub **username**
* GitHub **Personal Access Token** (as password)

✅ Output:

```
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 248 bytes | 248.00 KiB/s, done.
To https://github.com/username/my-first-repo.git
 * [new branch]      main -> main
```

---

### **11. Verify Changes on GitHub**

Open your GitHub repository in a browser.
You will now see `readme.txt` uploaded successfully.

---

## 🧾 **Result:**

Successfully created a new Git repository, added a file, committed it with a meaningful message, and pushed the changes to a remote GitHub repository.

---

## 🧠 **Conclusion:**

This experiment demonstrates the complete workflow of using Git for version control — from repository creation to remote synchronization. It helps developers track project versions and collaborate efficiently using Git and GitHub.

---

Would you like me to prepare this as a **formatted PDF report** (with command outputs, explanations, and screenshot placeholders) for your AWS/Git practical submission?
Here’s the **complete and report-ready guide** for your **Experiment 16: Set up a basic CI pipeline using Jenkins to build a “Hello World” project** — formatted for your **AWS + Ubuntu + Jenkins practical submission** 👇

---

## 🧪 **Experiment 16: Set Up a Basic CI Pipeline Using a CI/CD Tool (e.g., Jenkins) and Configure It to Build a Simple “Hello World” Application**

### **Objective:**

To understand and implement a basic Continuous Integration (CI) pipeline using **Jenkins** that automatically builds a simple “Hello World” project whenever changes are committed.

---

## 🖥️ **System Requirements**

* **AWS EC2 instance (Ubuntu)**
* **Jenkins** installed (server or Windows version)
* **Java (JDK 11 or above)** installed
* **Git** installed and connected to a remote repository
* **Sample project (Hello World)** — Java or Python program

---

## ⚙️ **Step-by-Step Procedure**

---

### **1. Install Java (Required for Jenkins)**

```bash
sudo apt update -y
sudo apt install openjdk-11-jdk -y
```

Check Java version:

```bash
java -version
```

---

### **2. Install Jenkins**

```bash
sudo apt install jenkins -y
```

Start and enable Jenkins service:

```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
```

Check status:

```bash
sudo systemctl status jenkins
```

---

### **3. Access Jenkins Dashboard**

Open a browser and go to:

```
http://<your-aws-public-ip>:8080
```

Get the initial admin password:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Copy the password → paste it in Jenkins setup wizard.

Select **Install Suggested Plugins**.

Create an **admin user** and complete setup.

---

### **4. Verify Jenkins Installation**

Once inside the dashboard → click **“Manage Jenkins” → “System Information”**
✅ Jenkins is successfully running.

---

### **5. Install Git Plugin (if not already installed)**

In Jenkins:

* Go to **Manage Jenkins → Manage Plugins → Available tab**
* Search for **Git Plugin**
* Install it and restart Jenkins.

---

### **6. Create a Simple “Hello World” Project**

Example (Java):

```bash
mkdir hello-world
cd hello-world
```

Create file `HelloWorld.java`:

```bash
nano HelloWorld.java
```

Add code:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World from Jenkins!");
    }
}
```

Initialize Git and push to GitHub:

```bash
git init
git add .
git commit -m "Added HelloWorld.java"
git branch -M main
git remote add origin https://github.com/username/hello-world.git
git push -u origin main
```

---

### **7. Create a New Jenkins Pipeline Project**

In Jenkins:

1. Click **New Item**
2. Enter project name → e.g., `HelloWorldPipeline`
3. Choose **“Pipeline”** → Click **OK**

---

### **8. Configure the Pipeline**

Scroll down to the **Pipeline section** → choose **Pipeline script from SCM**

* **SCM**: Git
* **Repository URL**:

  ```
  https://github.com/username/hello-world.git
  ```
* **Branch**: main

Add pipeline script (either in Jenkinsfile or inline):

Example **Jenkinsfile** (inside your GitHub repo):

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the Hello World Project...'
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                echo 'Executing the program...'
                sh 'java HelloWorld'
            }
        }
    }
}
```

---

### **9. Save and Build the Pipeline**

Click **Save → Build Now**

✅ Output in console log:

```
[Pipeline] echo
Building the Hello World Project...
[Pipeline] sh
javac HelloWorld.java
[Pipeline] echo
Executing the program...
[Pipeline] sh
Hello, World from Jenkins!
Finished: SUCCESS
```

---

### **10. Verify Build Success**

Go to:

* **Build History → Last Build (#1)**
* Click **Console Output** to confirm successful execution.

---

## 🧾 **Result:**

Successfully created a basic **CI pipeline in Jenkins** that automatically builds and executes a simple “Hello World” project whenever changes are pushed to the GitHub repository.

---

## 🧠 **Conclusion:**

This experiment demonstrates how Jenkins can automate the process of **building and testing applications**. The CI pipeline ensures continuous integration, reducing manual effort and improving software delivery speed and reliability.

---

Would you like me to prepare this experiment as a **formatted PDF report (with commands, screenshots placeholders, and outputs)** for your AWS + Jenkins practical submission?
Here’s the **complete, step-by-step and report-ready write-up** for your **Experiment 17: Build a Docker image from a Dockerfile and run a Docker container using the built image** — formatted perfectly for your **AWS + Ubuntu lab report** 👇

---

## 🧪 **Experiment 17: Build a Docker Image from the Dockerfile and Run a Docker Container Using the Built Image**

### **Objective:**

To understand how to create a Dockerfile, build a Docker image from it, and run a Docker container using the created image.

---

## 🖥️ **System Requirements**

* **AWS EC2 Instance (Ubuntu)**
* **Docker** installed and running
* Basic knowledge of Linux commands

---

## ⚙️ **Step-by-Step Procedure**

---

### **1. Verify Docker Installation**

```bash
docker --version
```

✅ Output Example:

```
Docker version 27.0.3, build abc1234
```

---

### **2. Create a Working Directory**

```bash
mkdir docker-demo
cd docker-demo
```

---

### **3. Create a Dockerfile**

```bash
nano Dockerfile
```

Add the following content:

```dockerfile
# Use the official Ubuntu base image
FROM ubuntu:latest

# Set the working directory inside the container
WORKDIR /app

# Install dependencies
RUN apt update && apt install -y python3

# Copy files from host to container
COPY hello.py .

# Command to run the application
CMD ["python3", "hello.py"]
```

---

### **4. Create the Application File**

```bash
nano hello.py
```

Add the following code:

```python
print("Hello, World! This is my custom Docker image.")
```

---

### **5. Build the Docker Image**

Use the following command to build the image:

```bash
sudo docker build -t my-hello-app .
```

✅ Explanation:

* `-t` → Tag name (assigns a name to the image)
* `.` → Tells Docker to look for a Dockerfile in the current directory

✅ Example Output:

```
Successfully built 123abcd456ef
Successfully tagged my-hello-app:latest
```

---

### **6. Verify the Built Image**

```bash
sudo docker images
```

✅ Output Example:

```
REPOSITORY      TAG       IMAGE ID       CREATED          SIZE
my-hello-app    latest    123abcd456ef   1 minute ago     125MB
```

---

### **7. Run a Container Using the Built Image**

```bash
sudo docker run my-hello-app
```

✅ Output:

```
Hello, World! This is my custom Docker image.
```

---

### **8. Run Container in Interactive Mode (Optional)**

```bash
sudo docker run -it my-hello-app /bin/bash
```

Now you can explore inside the container.
Exit with:

```bash
exit
```

---

### **9. List Running Containers**

```bash
sudo docker ps
```

To view all containers (including stopped ones):

```bash
sudo docker ps -a
```

---

### **10. Stop and Remove Container (Optional Cleanup)**

```bash
sudo docker rm <container_id>
```

Remove image:

```bash
sudo docker rmi my-hello-app
```

---

## 🧾 **Result:**

Successfully created a **Dockerfile**, built a **custom Docker image**, and executed it to run a container displaying the message **“Hello, World! This is my custom Docker image.”**

---

## 🧠 **Conclusion:**

This experiment demonstrates the process of building Docker images from Dockerfiles and running containers from those images. Dockerfiles provide a repeatable, automated way to build portable application environments — ensuring consistency across systems.

---

Would you like me to generate a **formatted PDF report** (with command outputs, explanations, and screenshot placeholders) for this experiment too? It’ll be ready for direct submission.




