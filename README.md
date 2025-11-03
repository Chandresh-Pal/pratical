
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


