
````markdown
# Static Node.js Single Page Application Deployment on AWS EC2

This guide describes how to deploy a static Node.js single-page application (SPA) to an AWS EC2 Ubuntu instance using Apache HTTP Server.

---

## 📁 Project Overview

This is a simple static Node.js front-end project deployed on an Apache server running on an AWS EC2 Ubuntu instance.

---

## 🚀 Steps to Reproduce

### 1. Create Node.js Project (Locally)

```bash
mkdir my-static-site
cd my-static-site
# Add your static files (HTML, CSS, JS)
````

### 2. Initialize Git and Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<YourUsername>/<YourRepo>.git
git push -u origin main
```

---

### 3. Launch EC2 Instance

* OS: Ubuntu (latest LTS)
* Configure security group to allow:

  * **SSH** (port 22)
  * **HTTP** (port 80)

---

### 4. SSH into EC2 and Install Git

```bash
sudo apt update
sudo apt install git -y
```

---

### 5. Clone Your Repository

```bash
git clone https://github.com/<YourUsername>/<YourRepo>.git
cd <YourRepo>
```

---

### 6. Install Apache Server

```bash
sudo apt install apache2 -y
```

---

### 7. Deploy Your Static Files

```bash
sudo cp -r * /var/www/html/
```

(Optional: Remove the default index.html)

```bash
sudo rm /var/www/html/index.html
```

---

### 8. Start and Enable Apache

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

---

### 9. View in Browser

Visit:

```
http://<your-ec2-public-ip>
```

You should see your deployed static site.

---

## 🧰 Tools Used

* Node.js (for local development)
* Git & GitHub (version control)
* Apache2 (web server)
* AWS EC2 (Ubuntu server)

---

## 🔒 Security Note

Make sure your `.git` folder is not exposed publicly. Do **not** push any sensitive data or credentials into your GitHub repo.

---
```
