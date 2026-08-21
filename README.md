# Ubuntu Nginx Multi-Site Deployment

> **Project:** Host three independent static websites on a single Ubuntu EC2 server using Nginx server blocks and GoDaddy DNS.

![Architecture Diagram](architecture-diagram.png)

## 📌 Project Overview

This project demonstrates how to deploy **three separate static websites** on one **Ubuntu EC2 instance**.

Each website has its own directory and its own Nginx server block.  
GoDaddy DNS is used to connect the subdomains to the EC2 public IP.

### Websites

- ✈️ **Travel Website**
- 🏨 **Hotel Website**
- 💪 **Fitness Website**

## 🏗️ Architecture

The deployment follows this simple flow:

**Browser → GoDaddy DNS → Ubuntu EC2 → Nginx → Correct Website**

Nginx checks the requested hostname and sends the request to the matching website directory.

## 🛠️ Technologies Used

- AWS EC2
- Ubuntu Linux
- Nginx
- GoDaddy DNS
- Shell Scripting
- HTML
- Git / GitHub

## 📁 Website Structure

```text
/var/www/html/
├── travel/
│   └── travel.html
├── hotel/
│   └── hotel.html
└── fitness/
    └── fitness.html
```

## ⚙️ Nginx Configuration

Nginx site configurations are stored under:

```text
/etc/nginx/sites-enabled/
```

Example structure:

```text
/etc/nginx/sites-enabled/
├── travel.conf
├── hotel.conf
└── fitness.conf
```

Each configuration contains a separate **server block** for its website.

## 🌐 DNS Configuration

The subdomains are created in **GoDaddy DNS** and point to the EC2 public IP.

Example:

```text
travel.example.com   →   EC2 Public IP
hotel.example.com    →   EC2 Public IP
fitness.example.com  →   EC2 Public IP
```

This allows users to open each website directly through its subdomain.

## 🔄 Request Flow

1. User enters a website subdomain in the browser.
2. GoDaddy DNS resolves the subdomain to the EC2 public IP.
3. The request reaches the Ubuntu EC2 server.
4. Nginx receives the request.
5. Nginx checks the requested hostname.
6. The matching server block is selected.
7. Nginx serves the corresponding static HTML website.

## 📂 Important Paths

### Website files

```text
/var/www/html/
```

### Nginx site configurations

```text
/etc/nginx/sites-enabled/
```

### Example website roots

```text
/var/www/html/travel/
/var/www/html/hotel/
/var/www/html/fitness/
```

## 🧩 Project Highlights

- One EC2 server hosts three websites.
- Each website has an independent document root.
- Each website uses a separate Nginx server block.
- Different subdomains are used instead of different ports.
- GoDaddy DNS connects the subdomains to the EC2 server.
- The websites are static HTML pages.
- The deployment is easy to expand by adding another website directory and server block.

## 🎯 Final Result

The final setup provides:

```text
                  Ubuntu EC2
                      │
                    Nginx
          ┌───────────┼───────────┐
          ↓           ↓           ↓
       Travel       Hotel      Fitness
      Website      Website      Website
```

All three websites run independently from a **single Ubuntu EC2 server**.

## 👨‍💻 Project Learning

Through this project, the following practical concepts are covered:

- Ubuntu server administration
- Nginx installation and configuration
- Nginx server blocks
- Static website hosting
- Website directory structure
- GoDaddy DNS and subdomains
- EC2 deployment
- Shell scripting basics
- Git and GitHub project documentation
