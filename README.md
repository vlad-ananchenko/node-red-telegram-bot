# Telegram Bot on Node-RED

This repository contains **nodeRedPostgresTelegramBot**, built using Node-RED. The bot offers essential commands for managing contacts and their birthdays. Key features include user registration, adding contacts, viewing contacts and their birthdays, all of which are stored in a PostgreSQL database.

## Features

The bot supports the following commands:

1. `/start` - start the bot and register the user in the database 🚀
2. `/add [name] [YYYY-MM-DD]` - add a new contact's name and birthday ➕
3. `/contacts` - view all contacts previously saved by the registered user 📒
4. `/contacts [name]` - find the birthday of a contact by name 🎂"
5. `/delete` - permanently delete the registered user and all their contacts from the database ❌

The bot's responses to commands are localized and adapt to the user's language settings (English, Russian, and Ukrainian).

## Setup Instructions

### Prerequisites

- **Docker**: To run all services in isolated containers.
- **Docker Compose**: For orchestrating and managing multiple containers.
- **Node.js and npm**: Required for working with Node-RED.

### Environment Variables

You need to set up the following environment variables in a **.env** file to create your own bot based on this one. Some values are provided as test examples and can be used in your .env file, except for sensitive data:

```bash
DATABASE_URL="DATABASE_URL"
DATABASE_USER="DATABASE_USER"
DATABASE_PASSWORD="DATABASE_PASSWORD"
DATABASE_HOST="DATABASE_HOST"
DATABASE_PORT="5432"
DATABASE_NAME="DATABASE_NAME"
TELEGRAM_BOT_TOKEN="TELEGRAM_BOT_TOKEN"
TELEGRAM_BOT_API_URL_PREFIX="https://api.telegram.org/bot"
CLOUDFLARE_TUNNEL_TOKEN="CLOUDFLARE_TUNNEL_TOKEN"
NODE_RED_CREDENTIAL_SECRET="NODE_RED_CREDENTIAL_SECRET"
ADMIN_PASSWORD_HASH="ADMIN_PASSWORD_HASH"
READONLY_PASSWORD_HASH="READONLY_PASSWORD_HASH"
```

## Available npm scripts

1. **prestart** - installs dependencies inside data/node-red before starting the bot
2. **start** - starts the Docker containers
3. **logs** - displays logs for the Node-RED instance
4. **start:logs** - starts the Docker containers and view logs immediately
5. **stop** - stops all Docker containers.

## Live Editing and Deployment

This bot is hosted at [telegram.nodered.work](https://telegram.nodered.work), running through Docker containers on DigitalOcean. The platform is secured with a Cloudflare tunnel and interacts with a PostgreSQL database also deployed on DigitalOcean.

### Key Features of the Website:

- **Live Functionality Editing**: Depending on the user's credentials, the bot's functionality can be edited in real time, making it highly customizable.
- **Implementation Viewing**: Users with read-only access can view the bot's implementation without making any changes.
