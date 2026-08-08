AWS EC2 Web Application Hosting 🚀
📌 Project Overview

This project demonstrates how I hosted a web application on an Ubuntu EC2 instance using Apache Web Server.

The project includes EC2 instance creation, Security Group configuration, SSH connection, Apache installation, deployment of a simple web application, and accessing the application through the EC2 Public IPv4 address.

🛠️ Technologies Used
Amazon EC2
Ubuntu Linux
Apache Web Server
SSH
HTML
AWS Security Groups
🏗️ Architecture

User
↓
Internet
↓
EC2 Public IP
↓
Security Group
↓
Apache Web Server
↓
Web Application

🚀 Steps Performed
1. Created an EC2 Instance

I launched an Ubuntu EC2 instance on AWS.

The required instance settings were configured, including the instance type, key pair, and Security Group.

2. Configured Security Group

I configured the following inbound rules:

Type	Port	Source
SSH	22	My IP
HTTP	80	0.0.0.0/0

SSH (Port 22) was used to connect to the EC2 instance, while HTTP (Port 80) was used to allow users to access the web application.

3. Connected to EC2 Using SSH

I connected to the Ubuntu EC2 instance using SSH from my Windows computer.

SSH provides secure remote access to the EC2 instance and allows commands to be executed on the Ubuntu server.

4. Installed Apache Web Server

I updated the Ubuntu packages and installed Apache Web Server.

Commands used:

sudo apt update

sudo apt install apache2 -y

After installation, I checked the Apache service using:

sudo systemctl status apache2

Apache was successfully running on the EC2 instance.

5. Deployed the Web Application

I placed the web application files inside Apache's default web directory:

/var/www/html/

The main website file was:

index.html

Apache uses this directory to serve the website to users through HTTP.

6. Verified Apache Web Server

I checked whether Apache was listening on HTTP Port 80 using:

sudo ss -tulpn | grep :80

I also tested the Apache web server locally using:

curl -I http://localhost

The server returned:

HTTP/1.1 200 OK

This confirmed that Apache was running and successfully responding to HTTP requests.

7. Accessed the Web Application

Finally, I accessed the web application through the EC2 instance's Public IPv4 address.

http://YOUR-EC2-PUBLIC-IP

The web application was successfully displayed in the browser.🎉
