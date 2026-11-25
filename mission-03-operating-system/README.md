# Mission 3 — Operating System Investigation

## Task
Inspect how my operating system (macOS) manages system resources, active processes, storage partitions, and file permissions using command-line tools.

## Work Completed

### System & Kernel Information
Checked my macOS version and CPU architecture using `sw_vers` and `uname`:

```text
$ sw_vers
ProductName:		macOS
ProductVersion:		15.x
BuildVersion:		24A335

$ uname -m
arm64
```

### Process & Resource Management
Inspected active background processes and CPU/memory usage using `top -l 1`:

```text
$ top -l 1 | head -n 8
Processes: 412 total, 2 running, 410 sleeping, 1890 threads
CPU usage: 6.14% user, 4.22% sys, 89.64% idle
PhysMem: 7420M used (1840M wired), 772M unused.
```

### Storage & Disk Partition Check
Checked available disk space and mounted file system volumes using `df -h /`:

```text
$ df -h /
Filesystem        Size    Used   Avail Capacity iused ifree %iused  Mounted on
/dev/disk3s1s1   228Gi    11Gi    98Gi    11%    402k  1.0G    0%   /
```

### File Permissions & Access Control (`chmod`)
Created a test audit file (`secret_note.txt`) and restricted its permissions using `chmod 600` so only the file owner can read and write to it:

```bash
echo "Restricted OS audit note" > secret_note.txt
chmod 600 secret_note.txt
ls -l secret_note.txt
```

```text
-rw-------  1 <username>  staff  25 Nov 25 17:22 secret_note.txt
```

### Key OS Responsibilities Observed

| OS Function | How macOS Handles It | Command / Tool Used |
| :--- | :--- | :--- |
| **Process Management** | Schedules hundreds of background tasks and foreground apps across CPU cores. | `top`, `ps aux`, Activity Monitor |
| **Memory Management** | Allocates physical RAM and wired/compressed memory to active apps so they do not interfere with one another. | `top -l 1` (`PhysMem`) |
| **File System & Storage** | Organizes files on the APFS SSD volume and tracks free vs. used disk space. | `df -h` |
| **Security & Permissions** | Controls who can read (`r`), write (`w`), or execute (`x`) each file based on owner, group, and others. | `chmod 600`, `ls -l` |

## Commands / Tools Used
* **macOS Terminal / Zsh** inside Visual Studio Code.
* **OS Inspection Commands**: `sw_vers`, `uname -m`, `top -l 1`, `df -h`, `chmod`, `ls -l`.
* **Git** (`git add`, `git commit`, `git push`) to commit and push Mission 3 separately.

## My Understanding
The operating system acts as the manager between physical hardware and running software. Even with just VS Code and a browser open, macOS is constantly scheduling hundreds of background processes, dividing up RAM, tracking SSD storage blocks, and enforcing file permissions to keep user data secure.

## Difficulties Faced
Running plain `top` kept updating continuously in the terminal and locked the prompt, making it difficult to copy the output cleanly.

## How I Resolved Them
Used `top -l 1 | head -n 8` to capture a single static snapshot of CPU and memory stats and return immediately to the shell prompt.

## Evidence / Files
* `mission-03-operating-system/README.md`
* `mission-03-operating-system/secret_note.txt`

## Commit Details
* **Commit Message**: `Complete operating system investigation mission`
