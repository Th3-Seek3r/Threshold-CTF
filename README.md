# Threshold CTF

> A local Capture The Flag (CTF) platform template built with CTFd and Docker.

**Threshold CTF** is a ready-to-deploy local CTF platform template designed for cybersecurity training, workshops, labs, and CTF competitions.

The project packages the CTFd platform with Docker so that it can be deployed on a Kali Linux system with minimal configuration.

---

## 🚀 Features

* 🐳 Docker-based deployment
* 🖥️ Designed for local Kali Linux environments
* ⚡ Simple one-command startup
* 🛑 Simple shutdown script
* 🔧 CTFd-based platform
* 🧩 Ready for custom challenges
* 🏆 Supports CTF users, teams, flags, scoring, and challenges
* 📦 Portable project template

---

## 🏗️ Architecture

```text
                    Threshold CTF
                          │
                          ▼
                    Docker Compose
                          │
          ┌───────────────┼───────────────┐
          │               │               │
          ▼               ▼               ▼
       CTFd            Database          Redis
          │
          ▼
        Nginx
          │
          ▼
   http://127.0.0.1:8000
```

---

## 📋 Requirements

Before installing Threshold CTF, you need:

* Kali Linux
* Internet connection
* Docker
* Docker Compose
* Git
* Unzip

The first deployment requires an Internet connection because Docker may need to download images and dependencies.

---

# ⚙️ Installation

## 1. Update Kali

```bash
sudo apt update
```

Optional:

```bash
sudo apt full-upgrade -y
```

---

## 2. Install Docker

```bash
sudo apt install -y docker.io docker-compose git unzip
```

Verify Docker:

```bash
docker --version
```

Verify Docker Compose:

```bash
docker compose version
```

---

## 3. Start Docker

```bash
sudo systemctl enable --now docker
```

Verify:

```bash
sudo systemctl status docker
```

You should see:

```text
Active: active (running)
```

---

# 📦 Installation from the Repository

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Threshold-CTF.git
```

Enter the project directory:

```bash
cd Threshold-CTF
```

Make the startup script executable:

```bash
chmod +x START.sh
```

---

# ▶️ Start Threshold CTF

Run:

```bash
./START.sh
```

The first startup may take several minutes while Docker downloads and builds the required components.

Check the containers:

```bash
sudo docker compose ps
```

---

# 🌐 Access Threshold CTF

Once the containers are running, open your browser and visit:

```text
http://127.0.0.1:8000
```

or:

```text
http://localhost:8000
```

Complete the initial CTFd configuration through the web interface.

Set the CTF name to:

```text
Threshold CTF
```

---

# 🛑 Stop Threshold CTF

To stop the platform:

```bash
./STOP.sh
```

This stops the Docker containers without deleting the project files.

---

# 🔄 Restart Threshold CTF

After restarting Kali:

```bash
cd ~/Projects/Threshold-CTF
./START.sh
```

Then open:

```text
http://127.0.0.1:8000
```

---

# 🔍 Useful Commands

### Check running containers

```bash
sudo docker compose ps
```

### View all logs

```bash
sudo docker compose logs
```

### View CTFd logs

```bash
sudo docker compose logs ctfd
```

### Follow CTFd logs

```bash
sudo docker compose logs -f ctfd
```

### Restart containers

```bash
sudo docker compose restart
```

### Stop containers

```bash
sudo docker compose down
```

---

# 📁 Project Structure

```text
Threshold-CTF/
│
├── CTFd/
│   └── CTFd application source
│
├── Dockerfile
│
├── docker-compose.yml
│
├── .ctfd_secret_key
│
├── START.sh
│
├── STOP.sh
│
├── SETUP_GUIDE.md
│
└── README.md
```

---

# 🔐 Secret Key

The project contains:

```text
.ctfd_secret_key
```

This file is used by CTFd for cryptographic configuration.

**Do not publish the contents of this file publicly.**

If you fork or redistribute this project as a template, consider generating a new secret key for each deployment.

---

# 🧪 Creating Challenges

Once Threshold CTF is running, challenges can be created through the CTFd administrator interface.

Possible categories include:

* Web
* Cryptography
* Digital Forensics
* OSINT
* Reverse Engineering
* Binary Exploitation
* Mobile
* Hardware
* Miscellaneous

Challenges can include:

* Descriptions
* Hints
* Flags
* Files
* Points
* Difficulty
* Categories

---

# 🎯 Intended Use

Threshold CTF is intended for:

* Cybersecurity training
* Security workshops
* University labs
* Cybersecurity clubs
* Internal security exercises
* CTF competitions
* Beginner cybersecurity practice
* Security awareness activities

Only use challenges and infrastructure in environments where you have permission to conduct security testing.

---

# 🛠️ Troubleshooting

### Docker is not running

```bash
sudo systemctl start docker
```

Then:

```bash
./START.sh
```

### Permission denied when running START.sh

```bash
chmod +x START.sh
```

Then:

```bash
./START.sh
```

### Containers are not running

```bash
sudo docker compose ps
```

View logs:

```bash
sudo docker compose logs
```

### Threshold CTF does not load

Check whether port `8000` is being used:

```bash
sudo ss -tulpn | grep :8000
```

Then check the CTFd logs:

```bash
sudo docker compose logs ctfd
```

---

# 📚 Documentation

For the complete beginner installation instructions, see:

```text
SETUP_GUIDE.md
```

The guide walks through the installation from a fresh Kali Linux environment to running Threshold CTF locally.

---

# 🤝 Contributing

Contributions are welcome.

You can contribute by:

* Creating new challenges
* Improving documentation
* Improving the Docker configuration
* Creating themes
* Improving the startup scripts
* Reporting bugs
* Suggesting new features

Before submitting major changes, please open an issue to discuss the proposed change.

---

# 📌 Project Status

**Status:** Template / Development

Threshold CTF is currently designed as a local CTF platform template.

Future improvements may include:

* Custom Threshold CTF theme
* Custom logo and branding
* Challenge templates
* Automated challenge deployment
* Additional security-focused services
* Pre-built CTF challenge environments
* Competition deployment configuration

---

# 👤 Author

**Threshold CTF**

Built as a cybersecurity CTF platform template using:

* [CTFd](https://github.com/CTFd/CTFd)
* Docker
* Docker Compose
* Kali Linux

---

# 📄 License

This repository contains configuration and deployment material for a CTFd-based platform.

CTFd is an open-source project maintained by the CTFd community. Refer to the CTFd project repository and license for the underlying CTFd software.

---

## 🏴 Threshold CTF

**Capture. Learn. Cross the Threshold.**

* [Full Documentation, Source code, and Configuration](https://docs.google.com/document/d/1t2JaeOTWuZvAb6jZKslrXjGHlJ4ygoZmz9B9RC5RfkE/edit?usp=sharing).
