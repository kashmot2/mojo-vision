# Mojo Vision Service

A Google Colab-based screenshot service that gives Mojo the ability to "see" WebGL/3D content.

## How It Works

1. Run the Colab notebook (connects to T4 GPU)
2. Notebook starts a Flask server + ngrok tunnel
3. Mojo calls the ngrok URL to request screenshots
4. Returns base64 image that Mojo can analyze

## Setup

1. Open `vision_service.ipynb` in Google Colab
2. Runtime > Change runtime type > T4 GPU
3. Run all cells
4. Copy the ngrok URL and update TOOLS.md

## API

```
GET /screenshot?url=https://example.com
Returns: { "image": "base64...", "console": [...] }

GET /health
Returns: { "status": "ok", "gpu": "Tesla T4" }
```
