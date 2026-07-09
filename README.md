# CPU Scheduling Algorithm Calculator

An educational tool for visualizing and calculating CPU scheduling algorithms — **FCFS**, **Round Robin**, **SJF/SRTF**, and **Priority Scheduling**.

---

## Table of Contents

1. [Features](#features)
2. [Requirements](#requirements)
3. [Installation & Setup](#installation--setup)
   - [Option A — Desktop App (Windows)](#option-a--desktop-app-windows)
   - [Option B — Browser (No Installation)](#option-b--browser-no-installation)
   - [Option C — Mobile / PWA](#option-c--mobile--pwa)
4. [How to Use](#how-to-use)
5. [Supported Algorithms](#supported-algorithms)
6. [Troubleshooting](#troubleshooting)

---

## Features

- Interactive Gantt chart visualization
- Step-by-step process scheduling simulation
- Metrics output: Waiting Time, Turnaround Time, Response Time, CPU Utilization
- Four scheduling algorithms in one tool
- Works as a desktop app, in a browser, or as a mobile PWA

---

## Requirements

### Desktop App
- **Windows 10 or later**
- **Python 3.9 or later** — [Download Python](https://www.python.org/downloads/)
  - Make sure to check **"Add Python to PATH"** during installation
- **pywebview >= 4.0** (installed automatically via the steps below)

### Browser / Mobile
- Any modern web browser (Chrome, Edge, Firefox, Safari)
- No Python required

---

## Installation & Setup

### Option A — Desktop App (Windows)

**Quickest way — one double-click:**

Double-click **`setup.bat`** in the project root. It will:
1. Verify Python is installed and in PATH
2. Create the `.venv` virtual environment (skips if it already exists)
3. Install **pywebview** automatically
4. Offer to launch the app immediately

> If you don't have Python yet, download it from [python.org](https://www.python.org/downloads/) and check **"Add Python to PATH"** during installation. Then double-click `setup.bat` again.

**Manual steps (if you prefer the terminal):**

```powershell
python -m venv .venv
.venv\Scripts\pip install pywebview
```

Then run:

```powershell
.venv\Scripts\python desktop\app.py
```

Or double-click `desktop\run.bat`.

The app will open in its own desktop window.

**Optional — Create a Desktop Shortcut**

Double-click `desktop\install.bat` to create a shortcut on your Windows Desktop.
It will auto-run the setup steps above if the environment is not yet configured.
You can then right-click the shortcut to **Pin to Start** or **Pin to Taskbar**.

---

### Option B — Browser (No Installation)

Simply open `index.html` in any modern web browser:

1. Navigate to the project folder.
2. Double-click `index.html`.

No Python or installation required.

---

### Option C — Mobile / PWA

The `mobile/` folder contains a Progressive Web App (PWA) version.

1. Deploy the contents of the `mobile/` folder to any static hosting service (e.g., Netlify, GitHub Pages).
2. Open the deployed URL on your mobile device.
3. Use your browser's **"Add to Home Screen"** option to install it as an app.

> The `mobile/netlify.toml` file is pre-configured for deployment to [Netlify](https://netlify.com).

---

## How to Use

### 1. Select an Algorithm

Click one of the four tabs at the top of the app:
- **FCFS** — First Come First Served
- **Round Robin** — Fixed time quantum
- **SJF / SRTF** — Shortest Job First or Shortest Remaining Time First
- **Priority** — Priority-based scheduling

### 2. Add Processes

Click the **Add Process** button in the left sidebar. A modal dialog will appear where you enter:

| Field | Description |
|---|---|
| **Process Name** | Label for the process (e.g., P1, P2) |
| **Arrival Time** | The time unit when the process arrives in the ready queue |
| **Burst Time** | The CPU time required to complete the process |
| **Priority** | (Priority tab only) Lower number = higher priority |

Click **Add** to confirm. Repeat for each process.

### 3. Configure Algorithm Settings (if applicable)

- **Round Robin**: Set the **Time Quantum** value in the left sidebar before calculating.
- **SJF / SRTF**: Toggle between **SJF** (non-preemptive) and **SRTF** (preemptive) using the mode buttons.

### 4. Calculate

Click the **Calculate** button at the bottom of the sidebar. The right panel will display:

- **Gantt Chart** — a visual timeline of process execution
- **Results Table** — individual process metrics (Arrival, Burst, Completion, Turnaround, Waiting, Response times)
- **Summary Metrics** — average Waiting Time, Turnaround Time, Response Time, and CPU Utilization

### 5. Manage Processes

- Click the **✕** button on any process card to remove it.
- Click **Clear** to remove all processes for the current algorithm tab.

---

## Supported Algorithms

| Algorithm | Type | Description |
|---|---|---|
| **FCFS** | Non-preemptive | Processes are executed in the order they arrive |
| **Round Robin** | Preemptive | Each process gets a fixed time slice (quantum) in rotation |
| **SJF** | Non-preemptive | The process with the shortest burst time runs next |
| **SRTF** | Preemptive | At each unit, the process with the shortest remaining time runs |
| **Priority** | Non-preemptive | Process with the lowest priority number runs first |

---

## Troubleshooting

**"Virtual environment not found" error when running `run.bat`**
> Double-click `setup.bat` in the project root — it will create the environment and install pywebview automatically. Or run manually: `python -m venv .venv` then `.venv\Scripts\pip install pywebview`

**The app window is blank or fails to load**
> Make sure `index.html` exists in the project root folder (one level above `desktop/`).

**`python` is not recognized as a command**
> Python is not added to your system PATH. Reinstall Python and check the **"Add Python to PATH"** option, or use the full path to your Python executable.

**pywebview installation fails**
> Try upgrading pip first: `.venv\Scripts\python -m pip install --upgrade pip`, then retry installing pywebview.
