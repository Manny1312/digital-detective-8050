# Mission 4 — Programs & Execution

## Task
Understand how source code becomes a running process, compare interpreted and compiled execution, inspect a live Process ID (PID) and exit status in Python, and trace how the terminal locates executable programs.

## Work Completed

### Locating the Interpreter & Tracing Program Execution
Used `which python3` to find where the Python interpreter lives on my MacBook, then ran `process_demo.py` with a command-line argument to inspect its live Process ID (PID) and exit code (`$?`).

```text
\$ which python3
/usr/bin/python3

\$ python3 process_demo.py test_arg
--- Program Execution Trace ---
Python Executable : /usr/bin/python3
Process ID (PID)  : 48219
Command Arguments : ['process_demo.py', 'test_arg']
Computed Sum      : 150
Status            : Execution finished cleanly (Exit Code 0)

 echo ?
0
```

### Interpreted vs. Compiled Execution

| Feature | Interpreted (e.g., Python) | Compiled (e.g., C / C++) |
| :--- | :--- | :--- |
| **How It Runs** | Translated and executed line-by-line at runtime by an interpreter (`python3`). | Translated all at once into machine code binary before execution. |
| **Output File** | Runs directly from the `.py` source file (caches `.pyc` bytecode internally). | Produces a standalone executable binary (like `a.out`). |
| **Error Detection** | Syntax errors stop execution immediately; runtime errors appear when that line runs. | Compiler catches syntax and type errors before any binary is created. |
| **Portability** | Same `.py` script runs on macOS, Linux, or Windows if Python is installed. | Must be compiled separately for each OS and CPU architecture (`arm64` vs `x86_64`). |

### Stages of Program Execution Observed

| Stage | What Happens | Example from This Mission |
| :--- | :--- | :--- |
| **Source Code** | Human-readable instructions saved in a file on the SSD. | Writing `process_demo.py` in VS Code. |
| **Command Lookup** | The shell checks `$PATH` to locate the requested program binary. | `which python3` locating `/usr/bin/python3`. |
| **Process Creation** | macOS loads the program into RAM and assigns a unique Process ID (PID). | OS assigning PID `48219` during runtime. |
| **Exit Status** | When finished, the program returns an integer code to the OS (`0` = success, non-zero = error). | `echo $?` returning `0`. |

## Commands / Tools Used
* **VS Code** to write `process_demo.py` and `README.md`.
* **Python 3** (`os`, `sys`, `time` modules) to inspect PID, interpreter path, and command-line arguments.
* **Terminal Commands**: `which python3`, `python3`, `echo $?`.
* **Git** (`git add`, `git commit`, `git push`) to save and push Mission 4 separately.

## My Understanding
A program stored on disk is just static text until the operating system loads it into RAM and assigns it a Process ID (PID). Because Python is interpreted, `python3` acts as the translator between my readable source code and the Apple Silicon CPU, and returning an exit code of `0` lets the shell or scripts know everything ran without errors.

## Difficulties Faced
At first, I wasn't sure how the terminal knew where `python3` was stored or how to verify whether a script succeeded programmatically without just reading print statements.

## How I Resolved Them
Used `which python3` to see how the shell resolves executables from `$PATH`, and tested `echo $?` right after running both a valid script (`0`) and a broken command (non-zero) to see exit codes in action.

## Evidence / Files
* `mission-04-programs/README.md`
* `mission-04-programs/process_demo.py`

## Commit Details
* **Commit Message**: `Complete programs and execution mission`