
# Instagram Auto-Poster (n8n Automation)

This repository provides a Dockerized setup for automating the posting of content to Instagram using [n8n](https://n8n.io/), an open-source workflow automation tool. It includes ngrok for secure tunneling and remote access.

## Main Aim
Automate posting images, videos, and other content to Instagram with minimal manual intervention. Easily schedule, manage, and monitor your Instagram posts using n8n workflows.

## Features
- **Instagram Automation**: Create workflows to post content to Instagram automatically
- **n8n**: Workflow automation platform running in a Docker container
- **ngrok**: Exposes n8n to the internet securely via a static domain
- **Persistent Data**: Workflow and credential data stored in a Docker volume
- **Environment Variables**: Configuration via `.env` file

## Prerequisites
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Setup
1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd n8n_automation
   ```
2. Create a `.env` file with the following variables:
   ```env
   N8N_ENCRYPTION_KEY=your_encryption_key
   NGROK_DOMAIN=your-ngrok-domain.ngrok.app
   NGROK_AUTHTOKEN=your_ngrok_authtoken
   GENERIC_TIMEZONE=Europe/Berlin
   ```
3. Start the services:
   ```bash
   docker compose up -d
   ```

## Usage
- Access n8n at `https://<your-ngrok-domain>.ngrok.app`
- The ngrok dashboard is available at `http://localhost:4041` (or your IP if it is not running on local server)
- Configure your Instagram credentials and workflows in the n8n editor
- Schedule or trigger Instagram posts automatically

## Useful Commands
- Start services: `docker compose up -d`
- Stop services: `docker compose down`
- View logs: `docker compose logs -f`

## Folder Structure
- `data/` - Persistent n8n data (excluded from git)
- `.env` - Environment variables (excluded from git)
- `docker-compose.yaml` - Docker Compose configuration

## .gitignore
See `.gitignore` for excluded files and folders (e.g., `data/`, `.env`, logs).

## License
MIT
