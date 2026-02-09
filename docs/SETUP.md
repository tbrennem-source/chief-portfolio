# Chief - Setup Guide

## Prerequisites

- Python 3.11+
- Telegram account
- Anthropic API key (Claude)
- Railway account (for cloud hosting)

## Quick Start

### 1. Clone and install

```bash
git clone https://github.com/tbrennem-source/chief-portfolio.git
cd chief-portfolio
pip install -r requirements.txt
```

### 2. Configure environment

```bash
cp .env.example .env
# Edit .env with your API keys
```

### 3. Create Telegram bot

1. Message [@BotFather](https://t.me/BotFather) on Telegram
2. Send `/newbot` and follow prompts
3. Copy the bot token to `TELEGRAM_BOT_TOKEN` in `.env`
4. Send a message to your bot, then get your chat ID from `https://api.telegram.org/bot<TOKEN>/getUpdates`
5. Set `TELEGRAM_CHAT_ID` in `.env`

### 4. Initialize database

```bash
python3 scripts/fix_database.py
```

### 5. Run locally

```bash
python3 scripts/bot_interactive.py
```

### 6. Deploy to Railway

```bash
# Install Railway CLI
npm install -g @railway/cli

# Login and deploy
railway login
railway init
railway up
```

## Optional: Google Calendar

1. Create a Google Cloud project
2. Enable Google Calendar API
3. Download `credentials.json` to project root
4. Run the bot once locally to complete OAuth flow (creates `token.json`)
5. Upload `token.json` to Railway

## Optional: Voice Messages

Set `OPENAI_API_KEY` in `.env` for Whisper transcription of voice messages.
