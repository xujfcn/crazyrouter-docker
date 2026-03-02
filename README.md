# 🐳 Crazyrouter Docker Configurations

> Docker Compose examples for running AI apps with Crazyrouter backend.

[Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community?ref=github) — One API key, 300+ models, 45% cheaper.

## 📋 Available Configurations

| App | Description | Port |
|-----|-------------|------|
| Open WebUI | ChatGPT-like interface | 3000 |
| LobeChat | Modern chat UI | 3210 |
| NextChat | Lightweight chat | 3001 |
| Dify | AI workflow platform | 80 |

## ⚡ Quick Start

### Open WebUI
```yaml
# docker-compose.yml
version: "3.8"
services:
  open-webui:
    image: ghcr.io/open-webui/open-webui:main
    ports:
      - "3000:8080"
    environment:
      - OPENAI_API_BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1
      - OPENAI_API_KEY=sk-your-crazyrouter-key
    volumes:
      - open-webui-data:/app/backend/data
    restart: unless-stopped

volumes:
  open-webui-data:
```

### LobeChat
```yaml
version: "3.8"
services:
  lobechat:
    image: lobehub/lobe-chat
    ports:
      - "3210:3210"
    environment:
      - OPENAI_API_KEY=sk-your-crazyrouter-key
      - OPENAI_PROXY_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1
    restart: unless-stopped
```

### NextChat (ChatGPT Next Web)
```yaml
version: "3.8"
services:
  nextchat:
    image: yidadaa/chatgpt-next-web
    ports:
      - "3001:3000"
    environment:
      - OPENAI_API_KEY=sk-your-crazyrouter-key
      - BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community
    restart: unless-stopped
```

### All-in-One Stack
```yaml
version: "3.8"
services:
  open-webui:
    image: ghcr.io/open-webui/open-webui:main
    ports: ["3000:8080"]
    environment:
      - OPENAI_API_BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1
      - OPENAI_API_KEY=sk-your-crazyrouter-key
    volumes: [open-webui-data:/app/backend/data]
    restart: unless-stopped

  lobechat:
    image: lobehub/lobe-chat
    ports: ["3210:3210"]
    environment:
      - OPENAI_API_KEY=sk-your-crazyrouter-key
      - OPENAI_PROXY_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community/v1
    restart: unless-stopped

  nextchat:
    image: yidadaa/chatgpt-next-web
    ports: ["3001:3000"]
    environment:
      - OPENAI_API_KEY=sk-your-crazyrouter-key
      - BASE_URL=https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community
    restart: unless-stopped

volumes:
  open-webui-data:
```

## 🔧 Usage

```bash
# Start single app
docker compose up -d

# Start all
docker compose -f all-in-one.yml up -d

# Update images
docker compose pull && docker compose up -d

# View logs
docker compose logs -f
```

## 🔗 Links
- 🌐 [Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community?ref=github)
- 💬 [Telegram](https://t.me/crzrouter)

## 📄 License
MIT

