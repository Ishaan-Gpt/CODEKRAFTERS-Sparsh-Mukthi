# Sparsh Mukthi - Advanced Gesture & Voice Control System

<div align="center">
  <img src="https://i.ibb.co/217zjLmn/temp.webp" alt="Sparsh Mukthi Logo" width="200"/>
  <p><i>Touchless Control System for Education, Healthcare, and VR Gaming</i></p>
  <p><b>Cross-Platform Solution for Windows, macOS, and Linux</b></p>
</div>

---

## 🚀 Live Demo
[Try the Website Here](https://sparsh-mukthi.vercel.app/)

---

## 🌟 Overview

Sparsh Mukthi is a comprehensive gesture recognition system designed for three key domains: Education, Healthcare, and VR Gaming. Built with modern computer vision technologies, it provides touchless interaction solutions particularly valuable in scenarios requiring hygiene (healthcare), immersive learning (education), and natural VR control (gaming).

### Key Features

- **Education & Healthcare Mode (edu-hcare.py)**:
  - Touchless interaction for sterile environments
  - Immersive learning experiences
  - Virtual anatomy manipulation
  - Presentation control for educators
  - COVID-safe interaction protocols

- **VR & Gaming Control (air-contol.py)**:
  - Natural VR navigation
  - Precise game control gestures
  - 3D space manipulation
  - Advanced gesture combinations
  - Smooth motion tracking

- **Voice Integration**:
  - Dual-mode voice control system:
    - **Command Mode**: Execute keyboard commands by voice
    - **Typing Mode**: Transcribe speech to text at cursor position
  - Natural language commands with customizable variants
  - Voice-gesture hybrid control for hands-free operation
  - Custom voice command mapping through web interface
  - Noise-resistant recognition using Vosk speech recognition
  - Real-time voice feedback and status indicators

- **Custom AI Gestures (Main Application)**:
  - Train personalized gestures
  - Map to keyboard/mouse actions
  - Real-time recognition
  - Modern cyberpunk interface
  - Extensible command system

## 🎯 Use Cases

### 1. Education Sector
- **Virtual Labs**: Touchless control of virtual experiments
- **3D Learning**: Manipulate 3D models in space
- **Interactive Presentations**: Control slides and demos with gestures
- **Distance Learning**: Enhanced remote instruction capabilities
- **Special Needs**: Adaptive learning interfaces

### 2. Healthcare Applications
- **Sterile Environments**: Touch-free computer control in operating rooms
- **Patient Care**: Contactless patient data access
- **Medical Imaging**: Gesture-based image manipulation
- **Rehabilitation**: Interactive physical therapy exercises
- **Infection Control**: COVID-safe workplace interactions

### 3. VR and Gaming
- **VR Navigation**: Natural movement in virtual spaces
- **Game Control**: Precise gesture-based commands
- **3D Modeling**: Intuitive object manipulation
- **Virtual Training**: Immersive simulation control
- **Fitness Games**: Body movement tracking

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Webcam or depth camera
- Git (for cloning)
- Windows/Linux/macOS
- Microphone (for voice control features)
- VR headset (optional, for VR features)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/vigneshbs33/CODEKRAFTERS-Sparsh-Mukthi
cd CODEKRAFTERS-Sparsh-Mukthi
```

2. Create and activate virtual environment:
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/macOS
python3 -m venv venv
source venv/bin/activate
```

3. Install dependencies:
```bash
# Windows
pip install -r requirements.txt
# Install voice recognition dependencies (not included in requirements.txt)
pip install vosk sounddevice pyttsx3 keyboard

# Linux
pip install -r requirements.txt
# Install voice recognition dependencies
pip install vosk sounddevice pyttsx3 keyboard
# For Linux, also install these system dependencies:
sudo apt-get update
sudo apt-get install -y python3-opencv python3-tk python3-dev portaudio19-dev ffmpeg

# macOS
pip install -r requirements.txt
# Install voice recognition dependencies
pip install vosk sounddevice pyttsx3 keyboard
# For macOS, install system dependencies via Homebrew:
brew install portaudio ffmpeg
```

4. Download the Vosk speech recognition model:
```bash
# Windows
python Voice-auto/download_vosk_model.py

# Linux/macOS
python3 Voice-auto/download_vosk_model.py
```

Alternatively, you can download the model manually from https://alphacephei.com/vosk/models and extract the `vosk-model-small-en-us-0.15` folder to the Voice-auto directory.

5. Platform-specific setup:

#### Windows
- Ensure Microsoft Visual C++ Redistributable is installed (required for some Python packages)
- Check camera permissions in Windows Settings → Privacy → Camera
- Check microphone permissions in Windows Settings → Privacy → Microphone

#### Linux
- Install X11 dependencies for GUI support:
  ```bash
  sudo apt-get install -y libx11-dev libxtst-dev
  ```
- Allow webcam access:
  ```bash
  sudo usermod -a -G video $USER
  ```
- Set up proper audio device permissions:
  ```bash
  sudo usermod -a -G audio $USER
  ```

#### macOS
- Grant camera permissions when prompted
- Grant accessibility permissions for controlling mouse/keyboard:
  System Preferences → Security & Privacy → Privacy → Accessibility
- Install XQuartz if needed for display:
  ```bash
  brew install --cask xquartz
  ```

### Starting the Application

Sparsh Mukthi's main interface is a Flask web application that provides access to all features:

```bash
python app.py
```

This will start the web server at http://127.0.0.1:5000 where you can access all functionality through a unified interface.

### Available Features

1. **Gesture Training & Recognition**
   - Train custom gestures with your webcam
   - Map gestures to keyboard commands
   - Use gestures to control applications

2. **Mouse Controllers**
   - **Education & Healthcare Mode** (EDU-HCARE): Precise cursor control for educational and medical applications
   - **Air Controller**: Gaming-optimized controller for FPS and other games

3. **Voice Control System**
   - **Voice Commands**: Control your computer with voice commands mapped to keyboard shortcuts
   - **Voice Typing**: Dictate text directly to any text field

4. **Demo Experiences**
   - **Education Demo**: Try the EDU-HCARE controller with 3D anatomy models
   - **Gaming Demo**: Experience the Air Controller with a browser-based FPS game

### System Architecture

The application consists of several interconnected components:

- **Main Web Interface** (`app.py`): Flask server providing the UI and controlling all subsystems
- **Gesture Recognition** (`gesture_data/adaptive-gesture-ai/`): Custom gesture training and recognition
- **Mouse Controllers** (`Main-flow-gesture/`): 
  - `edu-hcare.py`: Precision mouse control for education/medical use
  - `air-controller.py`: Specialized controller for gaming
- **Voice System** (`Voice-auto/`): Voice command and dictation capabilities

#### Voice Command Mode
- Speak commands to execute keyboard actions (e.g., "left", "right", "up", "down")
- Commands are processed when cursor is not in a text field
- Customizable command variants in commands.json
- Provides audio feedback when commands are recognized

#### Voice Typing Mode
- Speak naturally to type text where your cursor is positioned
- Works in any text field or text editor
- Special commands available:
  - "delete" or "backspace": Deletes the last character
  - "enter" or "new line": Creates a new line
  - "tab" or "indent": Inserts a tab
  - "space": Inserts a space
  - "clear all" or "clear": Clears all text
  - "stop typing" or "exit typing": Stops voice typing mode

4. **Custom AI Gestures**:
```bash
python app.py
```
- Access web interface at http://127.0.0.1:5000

```
sparsh-mukthi/
├─ app.py                    # Main Flask application with all controller routes
├─ requirements.txt          # Project dependencies
├─ Main-flow-gesture/        # Specialized mouse controllers
│   ├─ edu-hcare.py          # Education/Healthcare precision mouse controller
│   └─ air-controller.py     # Air gesture controller optimized for gaming
├─ Voice-auto/              # Voice control system
│   ├─ final-model.py        # Voice command recognition module
│   ├─ commands.json         # Voice command mappings configuration
│   └─ live_transcriber.py   # Real-time speech-to-text transcription
├─ gesture_data/            # Gesture recognition system
│   └─ adaptive-gesture-ai/  # Custom gesture training and prediction
│       ├─ collect_gestures.py # Gesture training module
│       ├─ predict_live.py     # Real-time gesture recognition
│       ├─ custom_gestures.json # Trained gesture database
│       └─ key_mappings.json   # Gesture-to-keyboard mapping
├─ static/                  # Web interface assets
├─ templates/               # HTML templates for web interface
└─ logs/                    # Application logs
```

### Core Components

1. **Main Application (`app.py`)**
   - Flask web server handling all HTTP routes
   - Process management for all controllers
   - User interface rendering
   - API endpoints for all functionalities

2. **Mouse Controllers**
   - **EDU-HCARE** (`edu-hcare.py`): Education and healthcare-oriented mouse controller with precise movements
   - **Air Controller** (`air-controller.py`): Gaming-optimized controller with special gestures for FPS games

3. **Voice System**
   - Command mode for executing keyboard shortcuts
   - Transcription mode for dictation
   - Vosk-based speech recognition

4. **Gesture Recognition**
   - Custom gesture training interface
   - Real-time gesture prediction
   - Keyboard/mouse action mapping

### Technologies Used

- **Core**: Python 3.8+, OpenCV 4.8+
- **AI/ML**: MediaPipe, NumPy, Scikit-learn, Joblib
- **VR Integration**: PyGame, AutoPy
- **Voice Processing**: Vosk, SoundDevice, Pyttsx3, Keyboard
- **Web Interface**: Flask, Flask-SocketIO
- **Input Control**: PyAutoGUI, Pynput
- **System Integration**: psutil (for process management)

## 🔄 Cross-Platform Compatibility

Sparsh Mukthi is designed to work across Windows, macOS, and Linux with minimal configuration differences. Here's how to ensure compatibility on each platform:

### Windows

- **Default Configuration**: Works out of the box on Windows 10/11
- **Process Management**: Uses Windows-specific process creation flags to avoid command prompt windows
- **Camera Access**: Automatically detects and uses the default camera
- **Dependencies**: All required libraries are installed via pip

### macOS

- **Permission Requirements**: Requires explicit permissions for camera, microphone, and accessibility
- **Dependency Management**: Some libraries (like portaudio) may require Homebrew installation
- **Process Management**: Uses POSIX-compliant process handling
- **Keyboard/Mouse Control**: Requires accessibility permissions to be granted in System Preferences

### Linux

- **Distribution Support**: Tested on Ubuntu 20.04+ and Debian-based distributions
- **System Dependencies**: Requires X11 libraries, OpenCV dependencies, and audio libraries
- **Device Access**: Requires appropriate user group permissions (video, audio)
- **Display Management**: May require X11 forwarding configuration in some environments

## 📦 GitHub Deployment

When cloning from GitHub, follow these additional steps to ensure a smooth experience:

1. **Dependencies Verification**:
   ```bash
   pip list | grep -E "opencv|numpy|mediapipe|flask|vosk"
   ```
   Ensure all critical dependencies are properly installed.

2. **First-Run Configuration**:
   ```bash
   python setup_check.py
   ```
   This will verify your system compatibility and set up any necessary configurations.

3. **Path Configuration**:
   Ensure all paths in the application are relative to the project root. If you encounter path-related errors, check:
   - File paths in app.py
   - Resource paths in templates/index.html
   - Model paths in Voice-auto/

4. **Environment Variables**:
   Create a `.env` file in the project root with any necessary environment variables for your platform:
   ```
   # Example .env file
   CAMERA_ID=0
   PYTHON_PATH=/usr/local/bin/python3  # Only if custom Python path is needed
   ```

### System Requirements

- **Minimum**:
  - CPU: Dual-core 2.0 GHz
  - RAM: 4GB
  - Camera: 720p 30fps
  - Microphone: Basic built-in
  - Storage: 500MB
  - Python 3.8 or newer

- **Recommended**:
  - CPU: Quad-core 2.5 GHz
  - RAM: 8GB
  - Camera: 1080p 60fps
  - Microphone: External with noise cancellation
  - Storage: 1GB for models and cached data
  - Python 3.10 or newer

## ⚠️ Troubleshooting

### Common Issues

#### Camera Not Working
1. **Access denied**: Check camera permissions in your OS settings
2. **Already in use**: Close other applications that might be using the camera
3. **Device not found**: Ensure webcam is properly connected and recognized by OS
4. **Driver issues**: Update camera drivers

#### Mouse Controller Problems
1. **Missing dependencies**: Run `pip install autopy pyautogui` manually
2. **Controller not starting**: Check console logs for specific errors
3. **Permission issues**: Run the application with appropriate permissions
4. **Platform compatibility**: Use the appropriate commands for your platform:
   - Windows: No additional steps needed
   - macOS: Grant accessibility permissions in System Preferences
   - Linux: Run `xhost +local:` before starting the application

#### Voice Recognition Not Working
1. **Missing Vosk model**: Download the model manually from https://alphacephei.com/vosk/models
2. **Microphone not detected**: Check microphone permissions and settings
3. **Audio input issues**: Select the correct input device in your OS settings

### Platform-Specific Issues

#### Windows
- If you encounter DLL loading errors, install the Visual C++ Redistributable
- For Python import errors, ensure you're using the virtual environment
- If using an older Windows version, run in compatibility mode

#### Linux
- For X11 errors: `export DISPLAY=:0` before running
- For camera issues: `ls -la /dev/video*` to verify camera device
- For permission errors: `chmod +x *.py` to make scripts executable

#### macOS
- For accessibility errors: Re-grant permissions in System Preferences
- For homebrew dependency issues: `brew doctor` to check system status
- For Python path issues: Use `python3` explicitly instead of `python`

### Getting Help

If you're still experiencing issues:
1. Check the console/terminal output for specific error messages
2. Open an issue on our [GitHub Issues page](https://github.com/vigneshbs33/CODEKRAFTERS-Sparsh-Mukthi/issues) with:
   - Your OS and version
   - Python version (`python --version`)
   - Complete error message
   - Steps to reproduce the issue
  - Microphone: Noise-canceling
  - Storage: 1GB
  - VR Ready GPU (for VR features)

## ⚙️ Configuration

### Education & Healthcare (edu-hcare.py)
```python
CAM_WIDTH, CAM_HEIGHT = 640, 480  # Camera resolution
FRAME_REDUCTION = 100             # Interaction zone
SMOOTHENING = 7                   # Motion smoothing
CLICK_THRESHOLD = 40              # Gesture detection sensitivity
```

### VR & Gaming (air-contol.py)
```python
ZOOM_THRESHOLD = 10    # VR zoom sensitivity
SCROLL_FACTOR = 20     # Movement multiplier
GRAB_THRESHOLD = 30    # Object grab detection
```

### Voice Control (Voice-auto/)
```python
# Command Mode (final-model.py)
SAMPLE_RATE = 16000    # Audio sampling rate
DURATION = 2           # Listen duration (seconds)
COOLDOWN = 1.5        # Command cooldown time
MODEL_PATH = "vosk-model-small-en-us-0.15"  # Voice model

# Transcription Mode (live_transcriber.py)
BLOCK_SIZE = 2048     # Lower latency for real-time
SHOW_PARTIAL = True   # Show partial results
WORDS_MODE = False    # Optimize for continuous speech
```

### Custom AI Gestures (app.py)
- Training frames: 30
- Detection confidence: 0.7
- Tracking confidence: 0.5

## 🔍 Troubleshooting

1. **Education/Healthcare Mode**:
   - Ensure proper lighting for sterile environments
   - Calibrate for specific room setup
   - Adjust sensitivity for medical gloves

2. **VR/Gaming Mode**:
   - Check VR device compatibility
   - Calibrate room-scale tracking
   - Optimize for game-specific gestures

3. **Custom AI Gestures**:
   - Improve training data quality
   - Adjust detection thresholds
   - Fine-tune gesture mappings

4. **Voice Integration**:
   - Check microphone permissions and settings
   - Calibrate ambient noise levels
   - Test in both command and transcription modes
   - Verify language settings
   - Update voice command dictionary
   - Adjust block size for latency vs accuracy
   - Fine-tune cooldown times for commands

## 🤝 Contributing

We welcome contributions! Areas of interest:

1. **Education**:
   - New learning interaction modes
   - Subject-specific gestures
   - Accessibility features

2. **Healthcare**:
   - Medical device integration
   - Sterile control patterns
   - Patient interaction modes

3. **VR/Gaming**:
   - Game-specific controls
   - VR environment integration
   - Performance optimization

## 🙏 Acknowledgments

- Healthcare professionals for sterile protocol guidance
- Educators for learning interface feedback
- VR developers for integration support
- Open source community

---

<div align="center">
  Made with ❤️ by CODEKRAFTERS<br>
  © 2025 Sparsh Mukthi. All rights reserved.
</div>
