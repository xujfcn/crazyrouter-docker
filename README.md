# 🐳 Crazyrouter Docker Configurations

> Docker Compose examples for running AI apps with Crazyrouter.

## Open WebUI
```yaml
services:
  open-webui:
    image: ghcr.io/open-webui/open-webui:main
    ports: ["3000:8080"]
    environment:
      - OPENAI_API_BASE_URL=https://crazyrouter.com/v1
      - OPENAI_API_KEY=sk-your-key
```

## LobeChat
```yaml
services:
  lobechat:
    image: lobehub/lobe-chat
    ports: ["3210:3210"]
    environment:
      - OPENAI_API_KEY=sk-your-key
      - OPENAI_PROXY_URL=https://crazyrouter.com/v1
```

## 🔗 [Crazyrouter](https://crazyrouter.com?ref=github)
## 📄 License: MIT
