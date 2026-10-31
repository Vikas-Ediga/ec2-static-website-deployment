# ec2-static-website-deployment

# ☁️ AWS EC2-Based Web Server | Static Website Hosting

<p align="center">
  <img src="https://img.shields.io/badge/AWS-Cloud%20Computing-orange?style=for-the-badge&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/EC2-Virtual%20Server-orange?style=for-the-badge&logo=amazonec2&logoColor=white" />
  <img src="https://img.shields.io/badge/Ubuntu-26.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" />
  <img src="https://img.shields.io/badge/Nginx-Web%20Server-009639?style=for-the-badge&logo=nginx&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <b>Deploying and hosting a static website on Amazon Web Services using EC2 and Nginx.</b>
</p>

---

## 📌 1. Project Introduction

This project focuses on deploying a static website using **Amazon Elastic Compute Cloud (EC2)** and configuring an **Nginx Web Server** on an Ubuntu Linux instance.

The main objective is to understand how cloud infrastructure works and how a web server can be configured to host and deliver website content over the internet.

In this project, I launched an Ubuntu-based EC2 instance, connected to it using SSH, installed Nginx, configured a custom HTML webpage, and successfully accessed the website through the instance's Public IPv4 address.

This project provides practical experience with AWS cloud services, Linux administration, networking, and web server configuration.

## 🎯 2. Project Objectives

- Understand the fundamentals of Amazon EC2.
- Launch and configure a cloud-based virtual server.
- Establish remote connectivity using SSH.
- Install and configure the Nginx web server.
- Deploy a custom static HTML webpage.
- Configure AWS Security Groups for HTTP access.
- Verify web server functionality using Linux commands.
- Access a cloud-hosted website through a public IP address.

## 🛠️ 3. Technologies & Tools Used

<p align="center">
  <img src="https://skillicons.dev/icons?i=aws,ubuntu,nginx,html,bash,linux&theme=light" />
</p>

| Technology | Description |
|---|---|
| Amazon EC2 | Provides cloud-based virtual server infrastructure |
| Ubuntu Linux | Operating system for the EC2 instance |
| Nginx | Web server used to serve the static website |
| HTML | Used to create the website content |
| SSH | Secure remote connection to the EC2 instance |
| Linux Commands | Used for server administration |
| AWS Security Groups | Controls inbound and outbound network traffic |

## ☁️ 4. AWS EC2 Instance Configuration

The following configuration was used during the project.

| Configuration | Details |
|---|---|
| Cloud Provider | Amazon Web Services |
| AWS Service | Elastic Compute Cloud (EC2) |
| Instance Name | MyWebServer |
| Instance Type | t3.micro |
| Operating System | Ubuntu 26.04.1 LTS |
| AWS Region | Asia Pacific (Mumbai) |
| Availability Zone | ap-south-1b |
| Web Server | Nginx |
| Website Type | Static Website |
| Protocol | HTTP |
| Port Number | 80 |
| Instance Status | Running during verification |

## 🏗️ 5. Project Architecture

The following architecture explains how a user accesses the website hosted on an AWS EC2 instance.

```text
                 👤 USER
                    |
                    |
                    ▼
              🌐 WEB BROWSER
                    |
                    |
                    ▼
           PUBLIC IPv4 ADDRESS
                    |
                    |
                    ▼
          🔐 AWS SECURITY GROUP
                 PORT 80
                    |
                    |
                    ▼
              ☁️ AMAZON EC2
              UBUNTU SERVER
                    |
                    |
                    ▼
               ⚙️ NGINX
              WEB SERVER
                    |
                    |
                    ▼
               📄 HTML FILE
                index.html
                    |
                    |
                    ▼
          WELCOME TO MY WEB SERVER
```

### 🔄 How the Architecture Works

1. A user enters the EC2 Public IPv4 address in a web browser.
2. The request reaches the AWS EC2 instance.
3. The Security Group allows incoming HTTP traffic through port 80.
4. Nginx receives the HTTP request.
5. Nginx locates the `index.html` file.
6. The HTML content is returned to the browser.
7. The user sees the hosted website.

## ⚙️ 6. Project Implementation

### Step 1: Launch an EC2 Instance

First, I accessed the AWS Management Console and navigated to the EC2 service.

Configuration performed:

- Selected Ubuntu as the operating system.
- Configured the instance name as `MyWebServer`.
- Selected the `t3.micro` instance type.
- Created or selected an existing key pair.
- Configured the Security Group.
- Allowed SSH traffic on port 22.
- Allowed HTTP traffic on port 80.
- Launched the EC2 instance.

### Step 2: Connect to the EC2 Instance

Connected to the Ubuntu server using SSH.

```bash
ssh -i your-key.pem ubuntu@YOUR_PUBLIC_IP
```

This established a secure connection between my local machine and the remote EC2 instance.

### Step 3: Update the Ubuntu Package Repository

Updated the package repository to get the latest available package information.

```bash
sudo apt update -y
```

### Step 4: Install Nginx

Installed Nginx on the Ubuntu EC2 instance.

```bash
sudo apt install nginx -y
```

### Step 5: Start and Enable Nginx

Started the Nginx service.

```bash
sudo systemctl start nginx
```

Enabled Nginx to start automatically whenever the server reboots.

```bash
sudo systemctl enable nginx
```

Verified the service status:

```bash
sudo systemctl status nginx
```

### Step 6: Configure the Static Website

Created a custom HTML webpage inside the Nginx document root.

```bash
echo "<h1>Welcome to My Web Server</h1>" | sudo tee /var/www/html/index.html
```

The webpage contains a simple heading:

```html
<h1>Welcome to My Web Server</h1>
```

### Step 7: Verify Nginx Configuration

Checked whether the Nginx configuration was valid.

```bash
sudo nginx -t
```

Verified the configured document root.

```bash
sudo nginx -T | grep root
```

### Step 8: Test the Website Locally

Used the curl command to verify the website from inside the EC2 instance.

```bash
curl localhost
```

Expected output:

```html
<h1>Welcome to My Web Server</h1>
```

### Step 9: Access the Website Through a Browser

Copied the EC2 Public IPv4 address and entered it into the browser.

```text
http://YOUR_PUBLIC_IP
```

The website was successfully displayed in the browser.

## 📸 7. Project Screenshots & Demonstration

The following screenshots demonstrate the successful implementation and deployment of the project.

### 🖥️ Screenshot 1 – AWS EC2 Instance

**Description:** The AWS Management Console shows the launched EC2 instance named `mywebserver`, its running status, instance type, and successful status checks.

<p align="center">
  <img src="./screenshots/ec2-instance.png" width="100%" alt="AWS EC2 Instance">
</p>

<p align="center">
  <b>Figure 1: EC2 Instance Running Successfully</b>
</p>

---

### 💻 Screenshot 2 – Ubuntu Terminal & Nginx Configuration

**Description:** The terminal demonstrates the Ubuntu environment, Nginx document root configuration, HTML webpage creation, and successful local testing using curl.

<p align="center">
  <img src="./screenshots/nginx-terminal.png" width="100%" alt="Nginx Configuration">
</p>

<p align="center">
  <b>Figure 2: Nginx Installation and Configuration</b>
</p>

---

### 🌐 Screenshot 3 – Successfully Hosted Static Website

**Description:** The deployed website is accessed through the EC2 instance's Public IPv4 address. The browser displays the custom webpage heading.

<p align="center">
  <img src="./screenshots/website-output.png" width="100%" alt="Hosted Static Website">
</p>

<p align="center">
  <b>Figure 3: Successfully Hosted Website Using AWS EC2</b>
</p>

---

## ✅ 8. Project Results

The project was successfully completed with the following results:

- Successfully launched an Ubuntu EC2 instance.
- Established SSH connectivity with the remote server.
- Installed and configured the Nginx web server.
- Created and deployed a custom HTML webpage.
- Verified the Nginx configuration.
- Tested the website using the curl command.
- Successfully accessed the website through the EC2 Public IPv4 address.

<p align="center">
  <img src="https://img.shields.io/badge/EC2-Running-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Nginx-Configured-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Website-Deployed-success?style=flat-square" />
</p>

## 🧠 9. Key Learnings

Through this project, I gained practical knowledge of:

**AWS Cloud Computing**
- Creating and managing EC2 instances.
- Understanding instance types and public IP addresses.
- Configuring AWS Security Groups.

**Linux Administration**
- Working with Ubuntu Linux.
- Installing and managing packages.
- Managing services using systemctl.
- Working with Linux directories and files.

**Web Server Management**
- Understanding how Nginx works.
- Configuring the web server document root.
- Hosting static HTML webpages.
- Testing web servers using curl.

**Networking**
- Understanding HTTP communication.
- Working with SSH connections.
- Understanding inbound traffic and network ports.

## ⚠️ 10. Challenges & Troubleshooting

During implementation, the following areas were important to verify:

| Issue | Solution |
|---|---|
| Website not accessible | Verified EC2 Security Group inbound rules |
| SSH connection failure | Checked SSH key, username and public IP |
| Nginx service not running | Checked service using systemctl |
| Incorrect website output | Verified the HTML file and document root |
| Configuration errors | Executed `sudo nginx -t` |

## 🚀 11. Future Enhancements

This project can be improved by implementing additional AWS services and DevOps practices.

- **Amazon Route 53:** Configure a custom domain name.
- **Amazon CloudFront:** Improve website delivery through content caching.
- **SSL/TLS:** Enable HTTPS for secure communication.
- **AWS CloudWatch:** Monitor EC2 instance performance.
- **CI/CD Pipeline:** Automate website deployment.
- **Infrastructure as Code:** Use Terraform to automate infrastructure provisioning.

## 🔐 12. Security & Resource Cleanup

For security and cost management:

- Restrict SSH access to trusted IP addresses.
- Allow HTTP traffic only when required.
- Use HTTPS and TLS certificates for production websites.
- Avoid sharing private SSH keys.
- Stop or terminate unused EC2 instances.
- Check for associated billable resources such as EBS volumes and Elastic IP addresses.

**Note:** This project uses HTTP for demonstration purposes, so browsers may display a "Not secure" warning. HTTPS has not been configured.

## 📂 13. Repository Structure

```text
EC2-Static-Website-Hosting/
│
├── README.md
│
└── screenshots/
    │
    ├── ec2-instance.png
    │
    ├── nginx-terminal.png
    │
    └── website-output.png
```

## 🎓 14. Conclusion

This project provided hands-on experience in deploying and managing a web server using Amazon EC2.

By combining Ubuntu Linux, Nginx, HTML, and AWS networking configurations, I successfully hosted a static website that can be accessed through a public IP address.

This project strengthened my understanding of cloud infrastructure, Linux server management, web hosting, and basic networking concepts.

It also provided a practical foundation for learning advanced AWS and DevOps technologies.

---

## 👨‍💻 About the Developer

**Vikas N D**

Cloud & DevOps Learner

Interested in Cloud Computing, AWS, Linux, Docker, Kubernetes, and DevOps technologies.

<p align="center">
  <a href="https://github.com/Vikas-Ediga">
    <img src="https://img.shields.io/badge/GitHub-Vikas--Ediga-181717?style=for-the-badge&logo=github" />
  </a>
  <a href="https://vikas-ediga.github.io/">
    <img src="https://img.shields.io/badge/Portfolio-Visit%20Website-blue?style=for-the-badge&logo=googlechrome&logoColor=white" />
  </a>
</p>

---

<p align="center">
  <b>☁️ Learning by Building | Building by Practicing | Growing in Cloud & DevOps 🚀</b>
</p>

<p align="center">
  ⭐ If you find this project useful, consider giving this repository a star!
</p>
