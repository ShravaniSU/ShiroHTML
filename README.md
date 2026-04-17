# 🐾 Shiro's Website

A simple, responsive static website dedicated to my pet dog **Shiro**, a 4-year-old Golden Retriever 💛

This project demonstrates how to build and deploy a static website using AWS EC2, a web server, and a custom domain.

---

## 🌐 Live Website

👉 https://shiro.shravaniurankar.xyz

---

## 📌 About Shiro

* 🐶 Name: Shiro
* 🎂 Age: 4 years
* 🐕 Breed: Golden Retriever
* 💛 Personality: Friendly, playful, loyal, and loving

Shiro is not just a pet, but a cherished member of the family who brings joy every single day.

---

## 🚀 Features

* Responsive design using Bootstrap
* Clean and modern UI
* Image gallery
* Contact section
* Smooth scrolling and basic interactivity
* Deployed on AWS EC2
* Custom domain with HTTPS

---

## 🛠️ Tech Stack

* HTML5
* CSS3
* Bootstrap 5
* JavaScript
* AWS EC2 (Ubuntu Server)
* Caddy (Web Server)
* Git & GitHub

---

## ⚙️ Deployment Steps

### 1. Launch EC2 Instance

* Ubuntu Server
* t2.micro (Free Tier)
* Open ports: 22 (SSH), 80 (HTTP), 443 (HTTPS)

---

### 2. Connect via SSH

```bash
ssh -i your-key.pem ubuntu@YOUR_PUBLIC_IP
```

---

### 3. Install Dependencies

```bash
sudo apt update
sudo apt install git -y
```

Install Caddy:

```bash
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /usr/share/keyrings/caddy-stable-archive-keyring.gpg > /dev/null
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy -y
```

---

### 4. Clone Repository

```bash
cd /var/www
sudo git clone https://github.com/YOUR_USERNAME/ShiroHTML.git
```

---

### 5. Set Permissions

```bash
sudo chown -R caddy:caddy /var/www/ShiroHTML
sudo chmod -R 755 /var/www/ShiroHTML
```

---

### 6. Configure Caddy

Edit Caddyfile:

```bash
sudo nano /etc/caddy/Caddyfile
```

Add:

```
shiro.shravaniurankar.xyz {
    root * /var/www/ShiroHTML
    file_server
}
```

---

### 7. Restart Server

```bash
sudo systemctl restart caddy
```

---

### 8. Access Website

Open in browser:

```
https://shiro.shravaniurankar.xyz
```

---

## 🔄 Updating the Website

After pushing changes to GitHub:

```bash
cd /var/www/ShiroHTML
sudo git pull
sudo systemctl restart caddy
```

---

## 🔐 HTTPS

HTTPS is automatically managed by Caddy using free SSL certificates.

---

## 🎯 Learning Outcomes

* AWS EC2 setup and configuration
* SSH access to remote servers
* Web server setup using Caddy
* Static website deployment
* Domain configuration and HTTPS setup

---

## 💛 Acknowledgment

Made with love for Shiro 🐾
