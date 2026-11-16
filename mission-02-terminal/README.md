# Mission 2 — Terminal Investigation

## Task
Navigate the macOS file system, create and organize folders and files, search inside text logs, and inspect hidden files strictly through command-line tools without using Finder.

## Work Completed

### Directory Navigation & Hidden Files
Used `pwd` to confirm my current directory path and `ls -la` to check hidden files and file permissions inside the mission folder.

```text
$ pwd
/Users/<username>/Desktop/digital-detective-8050/mission-02-terminal

$ ls -la
total 8
drwxr-xr-x   3 <username>  staff   96 Nov 15 23:45 .
drwxr-xr-x  13 <username>  staff  416 Nov 15 23:40 ..
-rw-r--r--   1 <username>  staff    0 Nov 15 20:15 README.md
```

### Creating, Copying, and Moving Files
Created a nested `case_files/evidence` folder structure, wrote an initial clue into a text file, made a backup copy, and renamed the original file:

```bash
mkdir -p case_files/evidence
echo "Clue 1: Unrecognized login attempt logged at 23:15" > case_files/notes.txt
cp case_files/notes.txt case_files/evidence/notes_backup.txt
mv case_files/notes.txt case_files/clue_01.txt
```

### Reading & Searching Text Files
Verified the file contents, searched for matching keywords, and located all `.txt` files across the directory tree using `cat`, `grep`, and `find`:

```text
\$ cat case_files/clue_01.txt
Clue 1: Unrecognized login attempt logged at 23:15

\$ grep -i "login" case_files/clue_01.txt
Clue 1: Unrecognized login attempt logged at 23:15

\$ find . -name "*.txt"
./case_files/clue_01.txt
./case_files/evidence/notes_backup.txt
```

### Summary of Commands Tested

| Command | Purpose | Example Used |
| :--- | :--- | :--- |
| `pwd` | Prints the full path of the current working directory. | `pwd` |
| `ls -la` | Lists all files (including hidden `.` files) along with permissions and sizes. | `ls -la` |
| `mkdir -p` | Creates nested directories in a single step without errors. | `mkdir -p case_files/evidence` |
| `cp` / `mv` | Copies or moves/renames files and folders. | `mv case_files/notes.txt case_files/clue_01.txt` |
| `cat` | Displays the full contents of a text file in the terminal. | `cat case_files/clue_01.txt` |
| `grep` | Searches for specific text patterns inside files. | `grep -i "login" case_files/clue_01.txt` |
| `find` | Searches a directory tree for files matching a specific name or extension. | `find . -name "*.txt"` |

## Commands / Tools Used
* **macOS Terminal / Zsh** inside Visual Studio Code.
* **CLI Commands**: `pwd`, `cd`, `ls -la`, `mkdir -p`, `echo`, `cp`, `mv`, `cat`, `grep`, `find`, `history`.
* **Git** (`git add`, `git commit`, `git push`) to save and upload Mission 2 separately.

## My Understanding
Using the terminal gives direct control over files and directories without relying on a graphical interface. Command flags like `ls -la` reveal hidden dotfiles and permissions that Finder hides by default, while `grep` and `find` make searching through logs and folders much faster.

## Difficulties Faced
I initially tried running `rm` on a folder without any flags and got an `"is a directory"` error. I also noticed that `pwd` and `ls -la` display my local MacBook username, which should not be published publicly.

## How I Resolved Them
Learned that deleting non-empty directories requires `rm -r`, and replaced my local username with `<username>` in the pasted terminal output to keep personal system details private.

## Evidence / Files
* `mission-02-terminal/README.md`
* `mission-02-terminal/case_files/clue_01.txt`
* `mission-02-terminal/case_files/evidence/notes_backup.txt`

## Commit Details
* **Commit Message**: `Complete terminal investigation mission`