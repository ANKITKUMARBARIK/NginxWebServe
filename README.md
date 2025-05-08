
# 🚀 NginxWebServe 🕸️

A simple, beginner-friendly project to help you understand how to install, configure, and serve static content using **Nginx** inside a **Docker-based Ubuntu container**.

---

## 📦 Project Overview

This project sets up:
- 🐳 Ubuntu container via Docker
- 🌐 Nginx web server installation
- 📝 Custom `nginx.conf` configuration
- 🖼 Static website serving (HTML + CSS)

---

## 🛠 Tech Stack

- Docker 🐳
- Ubuntu 🐧
- Nginx 🌐
- HTML & CSS 🎨
- Vim (for editing) 💻

---

## 🧰 Steps to Reproduce

### 1. Pull Ubuntu image

```bash
docker pull ubuntu
```

### 2. Run container with port mapping

```bash
docker run -it -p 8000:80 ubuntu
```

### 3. Inside container: Update & install Nginx

```bash
apt-get update
apt-get install nginx
```

### 4. Start Nginx

```bash
nginx
```

Check browser at 👉 `http://localhost:8000`

---

## ✍️ Edit Nginx Configuration

### Backup original file:

```bash
mv /etc/nginx/nginx.conf /etc/nginx/nginx-backup.conf
```

### Create new config

```nginx
events {}

http {
    include /etc/nginx/mime.types;
    server {
        listen 80;
        server_name _;
        root /etc/nginx/website;
    }
}
```

Then reload:

```bash
nginx -s reload
```

---

## 🌐 Add Static Files

```bash
mkdir /etc/nginx/website
cd /etc/nginx/website

# Create index.html
touch index.html

# Create style.css
touch style.css
```

Then add HTML & CSS content using vim or your favorite editor.

---

## ✅ Test Configuration

```bash
nginx -t
nginx -s reload
```

Then open your browser again: `http://localhost:8000`

---

## 📄 License

This project is open-source and free to use for educational purposes.

---

Happy Learning! 💡✨
