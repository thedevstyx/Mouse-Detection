# Mouse Movement User Identification

A browser-based system that identifies users by their mouse movement patterns using TensorFlow.js and deep learning.

## Quick Start

1. Download the files:
   ```bash
   git clone <repository-url>
   cd mouse-movement-identification
   ```

2. Open `index.html` in Chrome (recommended) or any modern browser.

## How to Use

### 1. Register Users (minimum 2)
- Enter username
- Click "Start Recording"
- Move mouse naturally for 30-60 seconds
- Click "Stop Recording"
- Repeat for another user

### 2. Train Model
- Click "Train Neural Network Model"
- Wait for training completion (~1-2 minutes)
- Watch progress bar

### 3. Identify Users
- Click "Start Identification"
- Move mouse naturally
- Watch real-time predictions
- Click "Stop" when done

## Requirements
- Modern web browser (Chrome recommended)
- GPU with WebGL support
- 4GB RAM minimum

## Technical Overview
- Neural Network: 6 layers (64→48→32→24→16→output)
- GPU-accelerated using WebGL
- Real-time predictions
- No server needed - runs entirely in browser

## Troubleshooting
If high CPU usage:
1. Enable hardware acceleration in browser
2. Check console (F12) for GPU status
3. Close other intensive tabs

## Code Structure
```
index.html          # Single file application containing:
  ├── Neural Network Model
  ├── GPU Acceleration
  ├── Data Collection
  └── User Interface
``` 