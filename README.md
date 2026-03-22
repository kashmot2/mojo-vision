# Mojo Vision

A Google Colab-based screenshot service that captures WebGL/3D content using a GPU-accelerated headless Chrome browser.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000?logo=flask&logoColor=white)
![Google Colab](https://img.shields.io/badge/Colab-F9AB00?logo=googlecolab&logoColor=white)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kashmot2/mojo-vision/blob/master/vision_service.ipynb)

## How It Works

1. Run the notebook on a free Colab T4 GPU
2. Flask server starts with an ngrok tunnel
3. Send a URL to the API — it captures a screenshot with full WebGL support
4. Returns a base64 image for analysis

## Quick Start

1. Click the **Open in Colab** badge above
2. Runtime > Change runtime type > **T4 GPU**
3. Run all cells
4. Copy the ngrok URL

## API

```
GET /screenshot?url=https://example.com&wait=3000
→ { "image": "base64...", "console": [...], "url": "..." }

GET /health
→ { "status": "ok", "gpu": "Tesla T4" }
```

## Why Colab?

Google Colab provides free access to NVIDIA T4 GPUs. Combined with Chrome's Vulkan + ANGLE flags, this gives full WebGL hardware acceleration in a headless environment.

Based on: [Supercharge Web AI Testing](https://developer.chrome.com/blog/supercharge-web-ai-testing)

## License

MIT

