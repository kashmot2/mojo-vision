# 👁️ Mojo Vision Service

A Google Colab-based screenshot service that gives Mojo the ability to "see" WebGL/3D content.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kashmot2/mojo-vision/blob/master/vision_service.ipynb)

## How It Works

1. Run the Colab notebook (connects to T4 GPU)
2. Notebook starts a Flask server + ngrok tunnel
3. Mojo calls the ngrok URL to request screenshots
4. Returns base64 image that Mojo can analyze

## Quick Start

1. Click the "Open in Colab" badge above
2. Runtime > Change runtime type > **T4 GPU**
3. Run all cells
4. Copy the ngrok URL and share with Mojo

## API

```
GET /screenshot?url=https://example.com&wait=3000
Returns: { "image": "base64...", "console": [...], "url": "..." }

GET /health
Returns: { "status": "ok", "gpu": "Tesla T4" }
```

## Why This Works

Google Colab's free tier provides access to NVIDIA T4 GPUs. Combined with the right Chrome flags (Vulkan, ANGLE), we get full WebGL hardware acceleration in a headless browser.

Based on: https://developer.chrome.com/blog/supercharge-web-ai-testing
