# 🎓 ITLA Calificaciones Bot

**Your grades, straight to Telegram.**

A Telegram bot that automatically scrapes your grades from ITLA's Campus Virtual using Selenium. Send `/notas` and receive an Excel file with all your subjects in seconds. Runs on Docker, hassle-free.

---

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram_Bot-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Chromium](https://img.shields.io/badge/Chromium-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)

---

## ✨ Features

### 🤖 Full Automation
- **Single Command** — Send `/notas` on Telegram and get your grades instantly
- **Smart Web Scraping** — Intercepts Campus Virtual API responses in real-time
- **Excel Export** — Receive a ready-to-open `.xlsx` file with formatted data

### 🔒 Security
- **Environment Variables** — Credentials stay out of the codebase, never exposed in the repo
- **Private Chat ID** — Only your Telegram account can interact with the bot
- **No Persistent Storage** — Data is generated on demand and never stored

### 🐳 Dockerized
- **One Command Setup** — `docker run` and you're good to go
- **Headless Chromium** — Browser included in the container, no GUI needed
- **Deploy Ready** — Compatible with any Linux server or VPS

---

## 🏗️ Architecture

```
├── ITLA_calificaciones_bot.py    # Main bot + scraping + export logic
├── Dockerfile                     # Container with Chromium + Python
├── requirements.txt               # Project dependencies
└── .gitignore                     # Sensitive file exclusions
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|:-----------|:--------|
| **Python 3.11** | Core language |
| **Selenium** | Web scraping + browser automation |
| **Chromium Headless** | Headless browser engine |
| **python-telegram-bot** | Telegram Bot API integration |
| **Pandas** | Data processing and export |
| **OpenPyXL** | Excel file generation |
| **Docker** | Containerization and deployment |

---

## 🚀 Getting Started

### Prerequisites
- Docker installed
- A Telegram bot (create one with [@BotFather](https://t.me/BotFather))
- Your Telegram Chat ID (get it from [@userinfobot](https://t.me/userinfobot))

### Installation

```bash
# Clone the repository
git clone https://github.com/JF012/ITLA_calificaciones_bot.git

# Navigate to the project
cd ITLA_calificaciones_bot

# Build the Docker image
docker build -t itla-bot .

# Run the container with your credentials
docker run -d \
  -e ITLA_EMAIL="your_email@itla.edu.do" \
  -e ITLA_PASSWORD="your_password" \
  -e BOT_TOKEN="your_botfather_token" \
  -e CHAT_ID="your_chat_id" \
  itla-bot
```

---

## ⚙️ Environment Variables

| Variable | Description |
|:---------|:------------|
| `ITLA_EMAIL` | Your ITLA Campus Virtual email |
| `ITLA_PASSWORD` | Your Campus Virtual password |
| `BOT_TOKEN` | Telegram bot token (via BotFather) |
| `CHAT_ID` | Your Telegram chat ID |

---

## 📱 Usage

| Step | Action |
|:----:|:-------|
| 1 | Open your bot on Telegram |
| 2 | Send `/notas` |
| 3 | Wait ~30 seconds |
| 4 | Receive your `calificaciones.xlsx` file |

---

## 🔧 How It Works

| Step | Detail |
|:-----|:-------|
| Login | Selenium opens Campus Virtual and logs in with your credentials |
| Interception | Injects a script that captures `GetCalificaciones` API calls |
| Extraction | Navigates to your profile and awaits the API response |
| Export | Converts the data into a DataFrame and generates the Excel file |
| Delivery | Sends the file directly to your Telegram chat |

---

## 📄 License

This project is open source and available for educational and portfolio purposes.

---

<p align="center">
  Made with Python 🐍 by <a href="https://github.com/JF012">JF012</a>
</p>
