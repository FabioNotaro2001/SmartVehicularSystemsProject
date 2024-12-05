# Advanced Driver Assistance System (ADAS)

This project implements a complex **Advanced Driver Assistance System (ADAS)** in the CARLA simulator. The system is designed to detect speed limits and traffic lights and take corrective measures, such as adjusting the vehicle's speed or stopping for red lights. The project also includes training notebooks to fine-tune detection models.

## Features
- **Speed Limit Detection:** Detects speed limit signs and adjusts the vehicle's speed accordingly.
- **Traffic Light Detection:** Identifies traffic lights and reports the color to the drive.
- **Manual and Autopilot Modes:** Allows manual control using a joystick or keyboard, and toggling between manual and autopilot modes.
- **Red Light Violation Detection:** Implements corrective braking for red light violations.

## Prerequisites

### Create a Conda Environment
Ensure you have Miniconda or Anaconda installed. Create a new Conda environment with Python 3.7.12, then activate it.

### Install Required Packages
Install all dependencies listed in the `requirements.txt` file after activating the environment.

## Project Structure
- **`notebook.ipynb`:** Contains the primary implementation of the ADAS system in the CARLA simulator.
- **`train.ipynb`:** Provides an example of training object detection models used for speed limit and traffic light recognition (YOLO).
- **`wheel_config.ini`:** Configuration file for joystick controls (e.g., Logitech G29 Racing Wheel).
- **`requirements.txt`:** Lists all required Python libraries.

## How to Run the Project

1. **Setup the Environment**
   Activate your Conda environment.

2. **Start CARLA 0.9.11 Simulator**
   Run the CARLA 0.9.11 server locally. Ensure you have CARLA installed and running on your machine. For more information, refer to the [CARLA installation guide](https://carla.readthedocs.io/en/latest/start_quickstart/).

3. **Run the Main Notebook**
   Open `main_notebook.ipynb` in your Jupyter Notebook or JupyterLab environment, and run the cells sequentially. The notebook includes:
   - Vehicle spawning
   - Camera setup for speed limit and traffic light detection
   - Event-driven vehicle control loop

4. **Train Models (Optional)**
   Use `train_notebook.ipynb` to train object detection models for speed limit and traffic light recognition. The training process is demonstrated with customizable configurations for your dataset.

## Key Functionalities

### Speed Control
The system uses a proportional control algorithm to adjust throttle and brake based on the detected speed limit:
- Gradual throttle increase when below the limit.
- Automatic braking when exceeding the limit.

### Traffic Light Detection
The system identifies the state of traffic lights and enforces stopping for red lights:
- Recognizes states: `Green`, `Yellow`, and `Red`.
- Activates emergency braking and hazard lights on red light violations.

### User Input and Control
- **Joystick Support:** Compatible with Logitech G29 Racing Wheel.
- **Keyboard Controls:** Supports manual steering (`A/D`), throttle (`W`), and brake (`S`).
- **Toggle Features:**
  - **`X`:** Speed Control
  - **`B`:** Autopilot
  - **`Y`:** Red Light Detection
  - **`L`:** Drive Gear
  - **`R`:** Reverse Gear

## Cleanup
To properly exit the simulation and release resources:
- Close the OpenCV display window.
- Quit the Pygame environment.
- Destroy CARLA actors such as vehicles and cameras.

## Demo
- **Live Vehicle Control:** Displays vehicle speed, detected traffic lights, and gear status on the screen.
- **Red Light Enforcement:** Stops the vehicle for red lights, demonstrating hazard light activation.

## Test Videos
- You can see the results in this [videos](https://liveunibo-my.sharepoint.com/:f:/g/personal/andrea_bedei2_studio_unibo_it/EvomtKkLIW1FrdYixnXoiIoBoFHtc72GQirlLdkI6mTG_w?e=bnGEdI)
- They are visible only for Unibo users, until 12/31/2025

## Notes
- Ensure that the CARLA server is running before launching the main notebook.
- Modify the configuration file `wheel_config.ini` for custom joystick mappings, if needed.
- Update model paths in the training notebook for custom datasets, id needed.

## License
This project is open-sourced under the MIT License. See the `LICENSE` file for details.

## Acknowledgements
- [CARLA Simulator](https://carla.org/) for providing a robust platform for ADAS testing.
- Python libraries such as TensorFlow, OpenCV, and PyGame for model training and control functionalities.
