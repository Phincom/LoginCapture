# Login Camera Logger

A simple Python application that captures a webcam image when started and saves a log entry with the date, time, and username.

## Features

* 📷 Webcam image capture
* 🕒 Timestamped image filenames
* 👤 Logs current Windows username
* 📝 Automatic log file creation
* 📁 Customizable save location
* 💾 Local image storage
* 🖥️ Windows compatible
* 🚀 Can be converted to a standalone EXE

---

## Requirements

* Windows 10/11
* Python 3.8+
* Webcam
* OpenCV

Install OpenCV:

```bash
pip install opencv-python
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/YourUsername/Login-Camera-Logger.git
```

Open the project folder:

```bash
cd Login-Camera-Logger
```

Install dependencies:

```bash
pip install opencv-python
```

---

## Configuration

Change the save location by editing:

```python
SAVE_FOLDER = os.path.join(
    os.environ["USERPROFILE"],
    "Save File Location",
    "Folder Name"
)
```

Example:

```python
SAVE_FOLDER = os.path.join(
    os.environ["USERPROFILE"],
    "Documents",
    "LoginCaptures"
)
```

All photos and logs will be stored in this folder.

---

## Running

Run the script:

```bash
python login_logger.py
```

---

## Output

Captured images:

```text
login_2026-01-01_12-30-45.jpg
```

Log file:

```text
login_log.txt
```

Example log entry:

```text
[2026-01-01 12:30:45] User: ExampleUser | Photo: login_2026-01-01_12-30-45.jpg
```

---

## Project Structure

```text
Login-Camera-Logger/
│
├── login_logger.py
├── README.md
│
├── login_log.txt
├── login_2026-01-01_12-30-45.jpg
│
└── dist/
    └── login_logger.exe
```

---

## Building an EXE

Install PyInstaller:

```bash
pip install pyinstaller
```

Build the executable:

```bash
pyinstaller --onefile login_logger.py
```

The EXE will be created in:

```text
dist/login_logger.exe
```

### Optional: Custom Icon

```bash
pyinstaller --onefile --icon=icon.ico login_logger.py
```

---

## Run on Startup

### Current User

1. Press `Win + R`
2. Type:

```text
shell:startup
```

3. Press Enter
4. Create a shortcut to `login_logger.exe`
5. Move the shortcut into the Startup folder

The application will now launch automatically when you sign in.

### All Users

1. Press `Win + R`
2. Type:

```text
shell:common startup
```

3. Press Enter
4. Place a shortcut to `login_logger.exe` in the folder

The application will start automatically for all users.

---

## Troubleshooting

### Camera Not Found

Make sure:

* A webcam is connected
* Camera permissions are enabled
* Another application is not using the camera

### EXE Closes Immediately

Open Command Prompt in the EXE folder and run:

```bash
login_logger.exe
```

This will show any error messages.

### OpenCV Not Installed

Install OpenCV:

```bash
pip install opencv-python
```

---

## Customization

### Change Image Filename Format

Edit:

```python
image_name = f"login_{timestamp}.jpg"
```

Examples:

```python
image_name = f"capture_{timestamp}.jpg"
```

```python
image_name = f"{USERNAME}_{timestamp}.jpg"
```

### Change Log Filename

Edit:

```python
LOG_FILE = os.path.join(SAVE_FOLDER, "login_log.txt")
```

Example:

```python
LOG_FILE = os.path.join(SAVE_FOLDER, "captures.txt")
```

### Change Camera Resolution

Edit:

```python
cap.set(cv2.CAP_PROP_FRAME_WIDTH, 640)
cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 480)
```

Example HD:

```python
cap.set(cv2.CAP_PROP_FRAME_WIDTH, 1280)
cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 720)
```

---

## Disclaimer

Use this software only on systems you own or administer and where all affected users are aware of and consent to its operation. Ensure compliance with applicable privacy laws, workplace policies, and local regulations.

---

## License

MIT License

---

Made with Python ❤️
