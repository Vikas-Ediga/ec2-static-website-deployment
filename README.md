# ☁️ AWS EC2 Static Website Hosting

<p align="center">
  <img src="https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws" />
  <img src="https://img.shields.io/badge/Ubuntu-Linux-E95420?style=for-the-badge&logo=ubuntu" />
  <img src="https://img.shields.io/badge/Nginx-Web%20Server-009639?style=for-the-badge&logo=nginx" />
  <img src="https://img.shields.io/badge/HTML-Website-E34F26?style=for-the-badge&logo=html5" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />
</p>

<p align="center">
  <b>Deploying and hosting a static website on AWS EC2 using Ubuntu Linux and Nginx Web Server.</b>
</p>

---

## 📌 1. Project Overview

This project demonstrates the deployment of a static website using **Amazon Elastic Compute Cloud (EC2)** and the configuration of an **Nginx Web Server** on an Ubuntu Linux instance.

The main objective is to understand cloud infrastructure, Linux server administration, web server configuration, and basic networking.

In this project, I launched an Ubuntu-based EC2 instance, connected to it using SSH, installed Nginx, configured a custom HTML webpage, and successfully accessed the website through the EC2 Public IPv4 address.

## 🎯 2. Project Objectives

- Understand Amazon EC2 and cloud computing.
- Launch and configure a virtual server.
- Connect to a remote server using SSH.
- Install and configure Nginx.
- Deploy a static HTML webpage.
- Configure AWS Security Groups.
- Allow HTTP traffic through port 80.
- Verify website accessibility through a public IP address.

## 🛠️ 3. Technologies Used

| Technology | Purpose |
|---|---|
| AWS EC2 | Cloud server hosting |
| Ubuntu 26.04.1 LTS | Operating system |
| Nginx | Web server |
| HTML | Website development |
| SSH | Remote server connection |
| Linux | Server administration |
| AWS Security Groups | Network traffic control |

## ☁️ 4. EC2 Instance Configuration

| Configuration | Details |
|---|---|
| Cloud Provider | Amazon Web Services |
| Service | EC2 |
| Instance Name | MyWebServer |
| Instance Type | t3.micro |
| Operating System | Ubuntu 26.04.1 LTS |
| Region | Asia Pacific (Mumbai) |
| Availability Zone | ap-south-1b |
| Web Server | Nginx |
| Protocol | HTTP |
| Port | 80 |
| Website Type | Static Website |

## 🏗️ 5. Project Architecture

```text
                 👤 USER
                    |
                    ▼
              🌐 WEB BROWSER
                    |
                    ▼
             PUBLIC IPv4 ADDRESS
                    |
                    ▼
          🔐 AWS SECURITY GROUP
                 PORT 80
                    |
                    ▼
              ☁️ AMAZON EC2
               UBUNTU SERVER
                    |
                    ▼
                ⚙️ NGINX
                WEB SERVER
                    |
                    ▼
               📄 index.html
                    |
                    ▼
          WELCOME TO MY WEB SERVER
```

### How It Works

1. User enters the EC2 Public IPv4 address in a browser.
2. AWS Security Group allows HTTP traffic through port 80.
3. The request reaches the EC2 instance.
4. Nginx receives the HTTP request.
5. Nginx serves the `index.html` file.
6. The webpage is displayed in the user's browser.

## ⚙️ 6. Project Implementation

### Step 1: Launch an EC2 Instance

- Open AWS Management Console.
- Navigate to EC2.
- Select Launch Instance.
- Choose Ubuntu as the operating system.
- Select t3.micro instance type.
- Create or select a key pair.
- Configure the Security Group.
- Allow SSH (Port 22) and HTTP (Port 80).
- Launch the EC2 instance.

### Step 2: Connect to EC2 Using SSH

```bash
ssh -i your-key.pem ubuntu@YOUR_PUBLIC_IP
```

### Step 3: Update Ubuntu Packages

```bash
sudo apt update -y
```

### Step 4: Install Nginx

```bash
sudo apt install nginx -y
```

### Step 5: Start and Enable Nginx

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

Verify Nginx status:

```bash
sudo systemctl status nginx
```

### Step 6: Create a Static Website

Create a custom HTML webpage:

```bash
echo "<h1>Welcome to My Web Server</h1>" | sudo tee /var/www/html/index.html
```

### Step 7: Verify Nginx Configuration

```bash
sudo nginx -t
```

Check the configured document root:

```bash
sudo nginx -T | grep root
```

### Step 8: Test Website Locally

```bash
curl localhost
```

Expected output:

```html
<h1>Welcome to My Web Server</h1>
```

### Step 9: Access the Website

Open your browser and enter:

```text
http://YOUR_PUBLIC_IP
```

The website should display:

**Welcome to My Web Server**

## 📸 7. Project Screenshots & Demonstration

The following screenshots demonstrate the successful implementation of the project.

### 🖥️ Screenshot 1 – AWS EC2 Instance

The EC2 instance was successfully launched and is running with all three status checks passed.

<p align="center">
  <img src="Screenshot%202026-10-29%20224623.png" alt="AWS EC2 Instance Running" width="100%">
</p>

<p align="center">
  <b>Figure 1: AWS EC2 Instance Running Successfully</b>
</p>

---

### 💻 Screenshot 2 – Nginx Configuration and Ubuntu Terminal

The Ubuntu terminal shows the Nginx configuration, document root verification, and successful website testing using curl.

<p align="center">
  <img src="Screenshot%202026-10-29%20225232.png" alt="Nginx Ubuntu Terminal Configuration" width="100%">
</p>

<p align="center">
  <b>Figure 2: Nginx Installation and Configuration</b>
</p>

---

### 🌐 Screenshot 3 – Successfully Hosted Static Website

The deployed static website is accessed through the EC2 Public IPv4 address and displays the custom HTML heading.

<p align="center">
  <img src="Screenshot%202026-10-29%20224422.png" alt="Static Website Hosted on AWS" width="100%">
</p>

<p align="center">
  <b>Figure 3: Static Website Successfully Hosted on AWS EC2</b>
</p>

---

## ✅ 8. Project Results

Successfully completed the EC2-based web hosting project.

- EC2 instance launched successfully.
- SSH connection established.
- Nginx installed and configured.
- Custom HTML webpage deployed.
- Nginx configuration verified.
- Website tested using curl.
- Website successfully accessed through the public IP address.

## 🧠 9. Key Learnings

### AWS Cloud Computing
- EC2 instance creation and management.
- Instance types and public IP addresses.
- Security Group configuration.

### Linux Administration
- Ubuntu Linux commands.
- Package installation and updates.
- Managing services using systemctl.
- Working with Linux directories.

### Web Server Management
- Nginx installation and configuration.
- Hosting static HTML webpages.
- Document root configuration.
- Web server testing using curl.

### Networking
- SSH connectivity.
- HTTP communication.
- Inbound network traffic.
- Port configuration.

## ⚠️ 10. Challenges & Troubleshooting

| Challenge | Solution |
|---|---|
| Website not accessible | Verified Security Group rules |
| SSH connection failure | Checked SSH key and public IP |
| Nginx not running | Verified service using systemctl |
| Incorrect website output | Checked HTML file and document root |
| Nginx configuration errors | Used `sudo nginx -t` |

## 🚀 11. Future Enhancements

The project can be enhanced by integrating additional AWS services and DevOps technologies.

- **Amazon Route 53:** Configure a custom domain.
- **Amazon CloudFront:** Improve content delivery.
- **SSL/TLS:** Enable HTTPS security.
- **Amazon CloudWatch:** Monitor server performance.
- **CI/CD Pipeline:** Automate website deployment.
- **Terraform:** Automate infrastructure provisioning.

## 🔐 12. Security & Resource Cleanup

- Restrict SSH access to trusted IP addresses.
- Configure appropriate Security Group rules.
- Use HTTPS for production websites.
- Never share private SSH keys.
- Stop or terminate unused EC2 instances.
- Check for remaining billable AWS resources.

**Note:** This project uses HTTP for demonstration purposes. HTTPS has not been configured.

## 📂 13. Repository Structure

```text
ec2-static-website-deployment/
│
├── README.md
│
├── Screenshot 2026-10-29 224422.png
│
├── Screenshot 2026-10-29 224623.png
│
└── Screenshot 2026-10-29 225232.png
```

## 🎓 14. Conclusion

This project provided practical experience in deploying and managing a web server using Amazon EC2.

By combining AWS cloud infrastructure, Ubuntu Linux, Nginx, HTML, and networking configurations, I successfully deployed a static website accessible through a public IPv4 address.

This project strengthened my understanding of cloud computing, Linux administration, web server management, and basic networking concepts.

It also provided a strong foundation for exploring advanced AWS and DevOps technologies.

---

## 👨‍💻 About the Developer

**Vikas N D**

Cloud & DevOps Learner

Interested in:

- Cloud Computing
- Amazon Web Services
- Linux Administration
- Docker
- Kubernetes
- DevOps

<p align="center">
  <a href="https://github.com/Vikas-Ediga">
    <img src="https://img.shields.io/badge/GitHub-Vikas--Ediga-181717?style=for-the-badge&logo=github">
  </a>
  <a href="https://vikas-ediga.github.io/">
    <img src="https://img.shields.io/badge/Portfolio-Visit%20Website-blue?style=for-the-badge&logo=googlechrome">
  </a>
</p>

---

<p align="center">
  <b>☁️ Learning by Building | Building by Practicing | Growing in Cloud & DevOps 🚀</b>
</p>

<p align="center">
  ⭐ If you find this project useful, consider giving this repository a star!
</p>
