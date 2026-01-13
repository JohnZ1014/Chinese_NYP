# Chinese_NYP 
ChineseNYP: Interactive Facial Style Transfer System

Overview
ChineseNYP is an interactive facial style transfer system inspired by Yangliuqing New Year Prints, a traditional Chinese folk art form.
The system captures real-time facial images via a camera, performs facial landmark detection and tracking, and generates stylized New Year Print–style portraits that preserve facial identity and spatial consistency.

The system integrates TouchDesigner, MediaPipe, and ComfyUI, and leverages Stable Diffusion, LoRA, ControlNet, and ResNet to achieve controllable, real-time facial style transfer with face tracking. Due to limited space, please download the file from Google Drive: https://drive.google.com/drive/folders/1-HUz4OBxROPJmSnfGcNyqNVkWGkr4e51?usp=sharing

System Requirements

Hardware
A 1080p USB camera
GPU with sufficient VRAM to run Stable Diffusion (e.g., NVIDIA RTX 3080)

Software

TouchDesigner 2023.11600 Pro

ComfyUI

MediaPipe

Python environment compatible with ComfyUI

Required Stable Diffusion dependencies

Installation and Setup
1. TouchDesigner Project Setup

Launch TouchDesigner 2023.11600 Pro.

Open the provided ChineseNYP TouchDesigner project file.

Add the following components to the Palette:

MediaPipe

comfyUI2TD

These components enable facial tracking and communication between TouchDesigner and ComfyUI.

2. Model Preparation (ComfyUI)

Place the ChineseNYP checkpoint model into the checkpoints/ directory of ComfyUI.

Place the ChineseFace LoRA model into the lora/ directory of ComfyUI.

Ensure that ControlNet and required ResNet-related components are correctly installed and configured in ComfyUI.

3. Launch ComfyUI

Start ComfyUI and verify that it is running correctly.

Confirm that the Stable Diffusion pipeline loads successfully with the ChineseNYP checkpoint and LoRA models.

Running the System

Open the TouchDesigner project.

Locate and click the ComfyUI node within the TouchDesigner network.

Establish a connection between TouchDesigner and ComfyUI.

Activate the camera input and ensure that MediaPipe successfully detects and tracks the user’s face.

Interaction Workflow

Facial Input
MediaPipe continuously captures and tracks facial landmarks from the live camera feed.

Gesture Trigger
A thumb gesture is used as the interaction trigger.
When the thumb gesture is detected:

The current facial image captured by MediaPipe is sent from TouchDesigner to ComfyUI.

Style Transfer
ComfyUI processes the facial image using:

Stable Diffusion (base generation)

LoRA (Yangliuqing New Year Print style adaptation)

ControlNet (facial structure and pose constraint)

ResNet-based optimization (identity and visual stability)

Result Feedback
The generated New Year Print–style facial image is sent back to TouchDesigner.
TouchDesigner then:

Displays the stylized result in real time

Continuously tracks facial position and movement to maintain spatial alignment

Notes

Generation latency depends on GPU performance and diffusion parameters.

A stable lighting environment is recommended for improved face detection accuracy.

This system is designed for interactive exhibitions, cultural visualization, and research demonstrations.
