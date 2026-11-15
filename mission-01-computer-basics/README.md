# Mission 1 — Know Your Computer

## Task
Trace a daily laptop activity using the IPOS model, identify my actual MacBook hardware and software, write a small Python script to verify my system specs, and examine three everyday computer systems.

## Work Completed

### Tracing an Activity with IPOS
**Activity:** Searching for a song on Spotify and playing it on my MacBook.

| Stage | What Happens | Hardware / Component Involved |
| :--- | :--- | :--- |
| **Input** | I click the search bar, type the song name, and hit Enter. | Built-in Trackpad and Keyboard |
| **Processing** | The app sends the search request, loads the audio stream, and decodes the sound data. | Apple Silicon Chip (CPU) and RAM |
| **Output** | The song plays through the speakers and the album cover appears on screen. | Built-in Speakers and Retina Display |
| **Storage** | My recent search history and cached audio data stay saved on disk so it loads faster next time. | Internal SSD |

### Hardware and Software on My System

#### Hardware

| Item | Type | What It Does |
| :--- | :--- | :--- |
| **Keyboard** | Input | Lets me type commands, code, and notes. |
| **Trackpad** | Input | Lets me move the cursor, click, and scroll. |
| **Retina Display** | Output | Shows everything visually on screen. |
| **Built-in Speakers** | Output | Plays audio from music, videos, and calls. |
| **Internal SSD** | Storage | Stores macOS, my apps, and my project folders permanently. |

#### Software

| Software | Type | What It Does |
| :--- | :--- | :--- |
| **macOS** | Operating System | Runs the laptop, manages memory and files, and connects apps to hardware. |
| **VS Code** | Application | Editor I use to write Python scripts, update README files, and run Git. |
| **Safari** | Application | Browser I use to check GitHub and read documentation. |
| **Activity Monitor** | Utility | Built-in tool I use to check CPU load, memory usage, and battery stats. |

### Computer Systems Around Me

| System | Main Purpose | One Input | One Output |
| :--- | :--- | :--- | :--- |
| **Namma Metro Ticket Machine** | Sells QR tickets and recharges metro smart cards. | Tapping the destination station on the touchscreen. | Printing the paper QR ticket. |
| **Bank ATM** | Lets users withdraw cash and check account balances. | Inserting a debit card and entering the PIN on the keypad. | Dispensing cash notes and displaying balance on screen. |
| **Washing Machine** | Automates washing and spinning clothes based on load settings. | Pressing the cycle dial and start button. | Spinning the drum and beeping when the cycle finishes. |

### Python IPOS & Hardware Verification (`system_check.py`)
I wrote a small script using Python's built-in `platform`, `os`, and `shutil` modules to demonstrate all four IPOS stages and check my MacBook's live core count and SSD space:

```text
--- Quick IPOS & System Check ---
Input Logged : Editing my README in VS Code
Processing   : Darwin (arm64) with 8 CPU cores
Storage Info : 120 GB free out of 256 GB
Saved output to ipos_log.txt!
```

## Commands / Tools Used
* **VS Code** to write `system_check.py` and format `README.md`.
* **Python 3** (`platform`, `os`, `shutil` modules) to check system specs and log IPOS output.
* **Git** (`git add`, `git commit`, `git push`) to commit and push Mission 1 separately.

## My Understanding
Every computing task follows the IPOS loop—taking input from the user, processing data in RAM via the CPU, giving visual or audio output, and saving files to the SSD. Even a 15-line Python script goes through all four stages when it reads user input, queries the OS, prints to the terminal, and writes a `.txt` log file.

## Difficulties Faced
At first, `shutil.disk_usage("/")` returned storage sizes in raw bytes, which produced a huge unreadable number.

## How I Resolved Them
I used integer division (`// (1024**3)`) in Python to convert raw bytes into gigabytes (GB) so the output was easy to read.

## Evidence / Files
* `mission-01-computer-basics/README.md`
* `mission-01-computer-basics/system_check.py`
* `mission-01-computer-basics/ipos_log.txt`

## Commit Details
* **Commit Message**: `Mission 1 README`
