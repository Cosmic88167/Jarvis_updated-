# Jarvis AI Assistant 2025

## Description

Jarvis is an advanced AI-powered personal assistant that combines voice recognition, face authentication, and a sleek web interface to provide a seamless user experience. Inspired by Iron Man's JARVIS, this project integrates multiple technologies to create an intelligent assistant capable of executing commands, responding to queries, and maintaining security through biometric authentication.

## Features

- **Face Authentication**: Secure login using facial recognition
- **Voice Commands**: Natural language processing for voice input
- **Hotword Detection**: Always-listening mode activated by "Jarvis"
- **Web Interface**: Modern, animated UI built with HTML/CSS/JS
- **Multiprocessing**: Efficient parallel processing for hotword and main functions
- **Command Execution**: Execute system commands, open applications, etc.
- **Text Input**: Alternative input method via chatbox
- **Settings**: Customizable options
- **Audio Feedback**: Sound effects and speech synthesis

## Architecture

The project follows a client-server architecture with multiprocessing:

### Flow Diagram

```
User Interaction
      |
      v
Hotword Detection (Process 2)
      |
      +--> Wake Word Detected --> Main Process (Process 1)
      |
      +--> No Wake Word --> Continue Listening

Main Process Flow:
1. Start Web Server (Eel)
2. Launch Browser (Edge in app mode)
3. Show Loading Animation
4. Face Authentication
      |
      +--> Success --> Hide Auth, Show Welcome
      |     |
      |     v
      |   Voice/Text Input Loop
      |     |
      |     +--> Process Command
      |     |     |
      |     |     +--> Execute Action
      |     |     +--> Respond via Speech/UI
      |     v
      |   Continue Listening
      |
      +--> Failure --> Retry Authentication
```

### Components

- **Frontend**: Web UI with animations, input forms, canvas for visualizations
- **Backend**: Python scripts handling logic, authentication, commands
- **Auth Module**: Face recognition using OpenCV and Haar cascades
- **Feature Module**: Hotword detection, speech processing
- **Command Module**: Command parsing and execution
- **Helper Module**: Utility functions
- **Config Module**: Configuration settings
- **DB Module**: Data storage (if applicable)

## Installation

### Prerequisites

- Python 3.8+
- Node.js (for any frontend dependencies, though not required)
- Webcam for face authentication
- Microphone for voice input
- Speakers for audio output

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Cosmic88167/Jarvis_updated-.git
   cd Jarvis-2025-master
   ```

2. Install Python dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Set up face recognition samples:

   - Place face images in `backend/auth/samples/`
   - Run trainer: `python backend/auth/trainer.py`

4. Configure settings in `backend/config.py`

## Usage

1. Run the application:

   ```bash
   python run.py
   ```

2. The browser will open automatically with the Jarvis interface.

3. Authenticate using face recognition.

4. Once authenticated, you can:
   - Say "Jarvis" to activate voice mode
   - Type commands in the chatbox
   - Use voice input via microphone button
   - Access settings

### Example Commands

- "Open browser"
- "What's the weather?"
- "Play music"
- "Set reminder"

## Project Structure

```
Jarvis-2025-master/
├── main.py                 # Main application entry point
├── run.py                  # Multiprocessing launcher
├── tempCodeRunnerFile.py   # Temporary file
├── backend/
│   ├── command.py          # Command processing
│   ├── config.py           # Configuration
│   ├── db.py               # Database operations
│   ├── feature.py          # Feature implementations
│   ├── helper.py           # Helper functions
│   └── auth/
│       ├── recoganize.py   # Face recognition
│       ├── sample.py       # Sample collection
│       ├── trainer.py      # Model training
│       ├── trainer/        # Trained models
│       ├── samples         # Face samples
│       └── haarcascade_frontalface_default.xml
├── frontend/
│   ├── index.html          # Main UI
│   ├── main.js             # Main JS logic
│   ├── controller.js       # UI controllers
│   ├── script.js           # Additional scripts
│   ├── style.css           # Styles
│   └── assets/
│       ├── img/            # Images
│       ├── audio/          # Sound files
│       └── vendore/        # Third-party libraries
├── .gitignore
└── README.md
```

## Technologies Used

- **Backend**: Python, Eel, OpenCV, Speech Recognition, Multiprocessing
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap, jQuery
- **Animations**: Lottie, Textillate, SiriWave
- **Audio**: PyAudio, gTTS
- **Face Recognition**: OpenCV Haar Cascades

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Future Enhancements

- Integration with more AI models
- Mobile app version
- Cloud synchronization
- Advanced NLP capabilities
