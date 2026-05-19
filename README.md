![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram_Bot-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Chromium](https://img.shields.io/badge/Chromium-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)

# 🎓 ITLA Calificaciones Bot

**Tus notas, directo a Telegram.**

Bot de Telegram que extrae automáticamente tus calificaciones del Campus Virtual del ITLA mediante web scraping con Selenium. Envía `/notas` y recibe un archivo Excel con todas tus materias en segundos. Corre en Docker, sin complicaciones.

---

## ✨ Features

### 🤖 Automatización Total
- **Comando /notas** — Un solo mensaje en Telegram y obtienes tus calificaciones
- **Web Scraping Inteligente** — Intercepta las respuestas del API del Campus Virtual en tiempo real
- **Exportación Excel** — Recibe un archivo `.xlsx` listo para abrir y compartir

### 🔒 Seguridad
- **Variables de Entorno** — Credenciales fuera del código, nunca expuestas en el repo
- **Chat ID Privado** — Solo tu cuenta de Telegram puede usar el bot
- **Sin Almacenamiento Persistente** — Los datos se generan bajo demanda y no se guardan

### 🐳 Dockerizado
- **Un Solo Comando** — `docker run` y listo, sin instalar dependencias manualmente
- **Chromium Headless** — Navegador incluido en el contenedor, sin necesidad de GUI
- **Listo para Deploy** — Compatible con cualquier servidor Linux o VPS

---

## 🏗️ Architecture

```
├── ITLA_calificaciones_bot.py    # Bot principal + scraping + exportación
├── Dockerfile                     # Contenedor con Chromium + Python
├── requirements.txt               # Dependencias del proyecto
└── .gitignore                     # Exclusión de archivos sensibles
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|:-----------|:--------|
| **Python 3.11** | Lenguaje principal |
| **Selenium** | Web scraping + automatización del navegador |
| **Chromium Headless** | Navegador sin interfaz gráfica |
| **python-telegram-bot** | Integración con la API de Telegram |
| **Pandas** | Procesamiento y exportación de datos |
| **OpenPyXL** | Generación de archivos Excel |
| **Docker** | Contenedorización y deploy |

---

## 🚀 Getting Started

### Prerequisites
- Docker instalado
- Un bot de Telegram (créalo con [@BotFather](https://t.me/BotFather))
- Tu Chat ID de Telegram (obténlo con [@userinfobot](https://t.me/userinfobot))

### Installation

```bash
# Clona el repositorio
git clone https://github.com/JF012/ITLA_calificaciones_bot.git

# Navega al proyecto
cd ITLA_calificaciones_bot

# Construye la imagen Docker
docker build -t itla-bot .

# Ejecuta el contenedor con tus credenciales
docker run -d \
  -e ITLA_EMAIL="tu_email@itla.edu.do" \
  -e ITLA_PASSWORD="tu_contraseña" \
  -e BOT_TOKEN="token_de_botfather" \
  -e CHAT_ID="tu_chat_id" \
  itla-bot
```

---

## ⚙️ Environment Variables

| Variable | Description |
|:---------|:------------|
| `ITLA_EMAIL` | Tu correo del Campus Virtual ITLA |
| `ITLA_PASSWORD` | Tu contraseña del Campus Virtual |
| `BOT_TOKEN` | Token del bot de Telegram (vía BotFather) |
| `CHAT_ID` | Tu ID de chat de Telegram |

---

## 📱 Usage

| Step | Action |
|:----:|:-------|
| 1 | Abre tu bot en Telegram |
| 2 | Envía `/notas` |
| 3 | Espera ~30 segundos |
| 4 | Recibe tu archivo `calificaciones.xlsx` |

---

## 🔧 How It Works

| Step | Detail |
|:-----|:-------|
| Login | Selenium abre el Campus Virtual e inicia sesión con tus credenciales |
| Intercepción | Inyecta un script que captura las llamadas a `GetCalificaciones` |
| Extracción | Navega al perfil y espera la respuesta del API |
| Exportación | Convierte los datos a DataFrame y genera el Excel |
| Entrega | Envía el archivo directamente a tu chat de Telegram |

---

## 📄 License

This project is open source and available for educational and portfolio purposes.

---

<p align="center">
  Made with Python 🐍 by <a href="https://github.com/JF012">JF012</a>
</p>
