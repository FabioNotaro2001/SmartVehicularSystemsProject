# Smart Vehicular Systems – ADAS in CARLA

An Advanced Driver Assistance System (ADAS) implemented in the CARLA simulator. The system detects speed limit signs and traffic lights to dynamically control vehicle speed and behavior for safe autonomous driving.

---

## 🚀 Features

- **Speed Limit Detection** –> identifies speed sign icons and adjusts throttle/brake using proportional control
- **Traffic Light Detection** –> detects red/yellow/green lights and enforces emergency braking on red light violations
- **Driving Modes** –> manual (keyboard or steering wheel) and Autopilot (toggle via joystick or keyboard)
- **Logging & Visualization** –> logs performance metrics with TensorBoard and logs test run data into Excel spreadsheets. 

---

## 🧩 Requirements

- **CARLA Simulator v0.9.11** (Ensure server runs on `localhost:2000`, matching client scripts.)  
- **Python 3.7.x** (tested in Conda).  
- **Hardware**:
  - Optional: Logitech G29 racing wheel or any compatible joystick (config via `wheel_config.ini`).  
  - GPU not strictly required; CPU works but slower for real-time detection.  

---

## 📁 Project Structure


/
├── notebook.ipynb # Main ADAS control logic via CARLA client
├── train.ipynb # Notebook to train or fine-tune detection models
├── manual_control_steeringwheel.py # Launches ADAS system with joystick support
├── requirements.txt # Python dependencies
├── wheel_config.ini # Steering wheel mapping
├── yolov8n.pt # Pre-trained YOLOv8 model weights
├── Report.pdf # Project report (slides or documentation)
└── runsFinLight/ runsSpeed/ runsUlt/ # Output folders for multiple ADAS test cases
:contentReference[oaicite:2]{index=2}

---

## ⚙️ Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/FabioNotaro2001/SmartVehicularSystemsProject.git
   cd SmartVehicularSystemsProject

Create and activate a Conda environment (or virtualenv)
conda create -n svs python=3.7
conda activate svs

Install dependencies
Install dependencies
Verify packages: carla, pygame, opencv-python, numpy, ultralytics, torch, etc.

Download CARLA Simulator 0.9.11
Follow instructions at CARLA docs and run:
./CarlaUE4.sh   # or equivalent on Windows

    Configure joystick/wheel settings (optional)
    Edit wheel_config.ini to match your input device. Default keyboard commands also supported.

▶️ Running the ADAS System
A. Keyboard mode
python notebook.ipynb

Run the notebook and follow cells to launch the simulation.
B. Joystick/steering-wheel modepython manual_control_steeringwheel.py
Toggle joystick support by editing the script or using launch flags.
📊 Training (Optional)

If you want to fine-tune detection models:

    Edit or modify train.ipynb.

    Specify dataset paths/more epochs as needed.

    Export the updated model and save it (e.g. as yolov8n-finetuned.pt).

    Replace the original yolov8n.pt or adjust path in scripts accordingly.
    ✅ Example Usage Flow

    Start CARLA via terminal or GUI.

    Activate your Python environment.

    Run notebook or script for behavior control.

    Observe live rendering and telemetry output.

    Logs and run output will populate into runsFinLight/, runsSpeed/, or runsUlt/ folders.
    Use Excel (testCarla.xlsx) to inspect numeric results.

    🧪 Testing Test Cases

The following scenarios are pre-configured:

    FinLight – Follow a sentinelled vehicle with brake/following logic.

    Speed – Respond dynamically to changing speed limit signs.

    Ult – Complex intersection scenarios with combined stimuli.
    The path to output for each test is recorded under the respective folder.
    📚 Academic Output

    A detailed project report is available as Report.pdf.

    Excel logs (testCarla.xlsx) include time-stamped speed, braking events, and violation occurrences.

📝 License & Credits

    Licensed under MIT License. See LICENSE.

    A collaborative project containing homework structure, originally tailored for Smart Vehicular Systems coursework.
    🎯 Tips

    Use keyboard mode if you don't have a joystick or want faster experimentation.

    For best performance, a dedicated GPU (e.g. RTX 20XX) is recommended, but CPU-only operation works with adjusted simulation speed.

    Modify control logic via editing the notebook.ipynb cells to integrate different datasets, detection thresholds, or reaction rules.

🧪 Contact / Feedback

For bug reports or suggestions, add an Issue on GitHub or email the project author. Happy to collaborate on further enhancements!

Enjoy exploring autonomous driving scenarios! Dynamic traffic environments await.
