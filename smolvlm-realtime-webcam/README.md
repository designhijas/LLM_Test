# SmolVLM Realtime Webcam

A web application that uses SmolVLM to perform real-time vision analysis through your webcam.

## Overview

This repository demonstrates how to use llama.cpp server with SmolVLM 500M to get real-time vision capabilities through your webcam. The application captures frames from your webcam at specified intervals and sends them to a SmolVLM server for analysis, displaying the AI's response in real-time.

## Features

- Real-time webcam capture and analysis
- Configurable analysis intervals (100ms to 2s)
- Custom instructions for the vision model
- Dark/Light theme toggle with persistent preference
- Clean, responsive UI with Bootstrap

## Setup Instructions

1. Install [llama.cpp](https://github.com/ggml-org/llama.cpp)

2. Run the SmolVLM server:
   ```
   llama-server -hf ggml-org/SmolVLM-500M-Instruct-GGUF
   ```
   
   **Notes:**
   - You may need to add `-ngl 99` to enable GPU (if you are using NVidia/AMD/Intel GPU)
   - You can also try other models from [llama.cpp multimodal models](https://github.com/ggml-org/llama.cpp/blob/master/docs/multimodal.md)

3. Open `index.html` in your browser or use a local server:
   ```
   # Using Python to create a simple HTTP server
   python -m http.server
   ```

4. Grant camera permissions when prompted by your browser.

5. Optionally change the instruction (for example, make it return JSON)

6. Click on "Start" and enjoy!

## Usage

1. Verify the Base API URL points to your SmolVLM server (default: http://localhost:8080)
2. Enter an instruction for the AI (e.g., "What do you see?")
3. Select the desired analysis interval
4. Click "Start" to begin the real-time analysis
5. Toggle between dark and light themes using the switch in the bottom-left corner

## How It Works

The application:
1. Captures frames from your webcam at the specified interval
2. Converts frames to base64-encoded JPEG images
3. Sends the image and your instruction to the SmolVLM server
4. Displays the AI's response in the interface

## Advanced Configuration

You can modify the following aspects of the application:
- Base API URL: Change this if your llama.cpp server is running on a different host or port
- Instruction: Customize the prompt sent to the vision model
- Interval: Adjust how frequently the application captures and analyzes frames

## Requirements

- A modern web browser with webcam access
- A running SmolVLM server
- The server should be running the SmolVLM-500M-Instruct-GGUF model or compatible multimodal model

## License

This project is licensed under the ISC License - see the LICENSE file for details.

## Acknowledgments

- Uses SmolVLM, a lightweight multimodal vision-language model
- Built with Bootstrap for responsive design