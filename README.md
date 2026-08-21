# Ubuntu Nginx Multi-Site Deployment

> **Project:** Host three independent static websites on a single Ubuntu EC2 server using Nginx server blocks and GoDaddy DNS.

## 🏗️ Architecture

![Architecture Diagram](architecture.png)

**Flow:** Browser → GoDaddy DNS → Ubuntu EC2 → Nginx → Travel / Hotel / Fitness

## 📌 Project Overview

This project demonstrates how to host three separate static websites on one Ubuntu EC2 server using Nginx.

- ✈️ Travel Website
- 🏨 Hotel Website
- 💪 Fitness Website
- 🌐 GoDaddy subdomains for website access
- ⚙️ Nginx server blocks for separate routing
- 🐧 Ubuntu Linux on AWS EC2

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

```text
/etc/nginx/sites-enabled/
├── travel.conf
├── hotel.conf
└── fitness.conf
```

Each website uses its own Nginx server block and website root.

## 🌐 GoDaddy DNS

Example subdomains:

```text
travel.premrrr.site
hotel.premrrr.site
fitness.premrrr.site
```

GoDaddy DNS connects the subdomains to the EC2 server, and Nginx selects the correct website.

## 🔄 Request Flow

1. User enters a website subdomain.
2. GoDaddy DNS resolves the subdomain.
3. The request reaches Ubuntu EC2.
4. Nginx receives the request.
5. Nginx checks the hostname.
6. The matching server block is selected.
7. Nginx serves the correct static website.

---

# 📸 Project Screenshots

Below are the screenshots in the exact project sequence.

## Step 1 — EC2 Instance Details

![Step 1 — EC2 Instance Details](screenshots/1.instance%20details.png)

## Step 2 — EC2 Instance Running State

![Step 2 — EC2 Instance Running State](screenshots/2.%20instance%20running%20state.png)

## Step 3 — SSH Login and PWD

![Step 3 — SSH Login and PWD](screenshots/3.%20ssh%20login%20pwd%20.png)

## Step 4 — Create and Run Shell Scripting File

![Step 4 — Create and Run Shell Scripting File](screenshots/4.%20create%20and%20run%20shell%20scipting%20file.png)

## Step 5 — Check Files Created by Shell Script

![Step 5 — Check Files Created by Shell Script](screenshots/5.%20after%20running%20the%20shell%20scripting%20file%20cheking%20files%20created%20or%20not.png)

## Step 6 — Shell Script Successfully Completed

![Step 6 — Shell Script Successfully Completed](screenshots/6.%20shell%20scipting%20file%20run%20ok%20msg%20seen%20%20succesfully.png)

## Step 7 — Add Server IP in GoDaddy

![Step 7 — Add Server IP in GoDaddy](screenshots/7.%20adding%20our%20server%20ip%20on%20go%20daddy.png)

## Step 8 — Add Website Subdomains

![Step 8 — Add Website Subdomains](screenshots/8.%20adding%20subdomains.png)

## Step 9 — Create and Configure Nginx Server Block Files

![Step 9 — Create and Configure Nginx Server Block Files](screenshots/9.%20creating%20cpnf%20files%20and%20editing%20it%20for%20our%20doamins%20and%20file%20path.png)

## Step 10 — Travel Website Output

![Step 10 — Travel Website Output](screenshots/10.%20travel%20website%20output.png)

## Step 11 — Hotel Website Output

![Step 11 — Hotel Website Output](screenshots/11.%20hotel%20website%20output.png)

## Step 12 — HTTPS Website Not Opening

![Step 12 — HTTPS Website Not Opening](screenshots/12.%20https%20thats%20y%20website%20not%20opening.png)

## Step 13 — HTTP Added and Fitness Website Output

![Step 13 — HTTP Added and Fitness Website Output](screenshots/13.%20remove%20httpds%20and%20add%20http%20then%20fitnesss%20website%20output.png)

## Step 14 — Server Blocks Reference

![Step 14 — Server Blocks Reference](screenshots/14.%20getting%20server%20blocks%20from%20chatgpt%20AI.png)

---

## 🎯 Final Result

```text
                    Ubuntu EC2
                        │
                      Nginx
             ┌──────────┼──────────┐
             ↓          ↓          ↓
          Travel      Hotel      Fitness
         Website     Website     Website
```

All three static websites run independently from a single Ubuntu EC2 server.

## 👨‍💻 Project Learning

- EC2 deployment
- Ubuntu Linux administration
- Nginx installation and configuration
- Nginx server blocks
- Static website hosting
- Website directory structure
- GoDaddy DNS and subdomains
- Shell scripting basics
- Git and GitHub project documentation
- Basic web troubleshooting