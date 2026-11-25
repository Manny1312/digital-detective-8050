# Mission 6 — Git & GitHub Workflow

## Task
Examine my repository's commit history, practice creating and merging a feature branch locally, inspect remote repository connections, and document core Git and GitHub workflows.

## Work Completed

### Inspecting Remote & Commit History
Verified my remote GitHub connection with `git remote -v` and reviewed my separate mission commits using `git log --oneline`:

```text
\$ git remote -v
origin  https://github.com (fetch)
origin  https://github.com (push)

\$ git log --oneline -n 6
a1b2c3d Test feature branch commit for Mission 6
e4f5g6h Complete numbers and data mission with number_converter.py
i7j8k9l Complete programs and execution mission
m0n1o2p Complete operating system investigation mission
q3r4s5t Complete terminal investigation mission
u6v7w8x Complete computer basics and IPOS mission
```

### Branching & Merging Practice
Created a separate branch (`mission-06-branch-test`), committed `branch_note.txt` on that branch without touching `main`, switched back to `main`, and merged the changes cleanly:

```bash
git checkout -b mission-06-branch-test
echo "Branch workflow verified" > mission-06-git-github/branch_note.txt
git add mission-06-git-github/branch_note.txt
git commit -m "Test feature branch commit for Mission 6"
git checkout main
git merge mission-06-branch-test
git branch -d mission-06-branch-test
```

### Core Git vs. GitHub Concepts

| Concept / Command | Role in Workflow |
| :--- | :--- |
| **Working Directory vs. Staging (`git add`)** | Lets me select specific mission files to include in a snapshot rather than committing everything at once. |
| **Commit (`git commit`)** | Saves a permanent, timestamped snapshot in local Git history with a clear message. |
| **Branch (`git checkout -b`)** | Creates an isolated workspace to test new code or edits safely without breaking `main`. |
| **Merge (`git merge`)** | Combines changes from a completed feature branch back into `main`. |
| **Remote Sync (`git push` / `git pull`)** | Uploads local commits to GitHub (`origin`) or downloads remote updates to my MacBook. |

## Commands / Tools Used
* **Git CLI** inside Visual Studio Code Terminal (`git status`, `git log --oneline`, `git remote -v`, `git checkout -b`, `git merge`, `git branch -d`, `git add`, `git commit`, `git push`).
* **GitHub** for hosting the remote repository and verifying commit history online.

## My Understanding
Git tracks version history locally through snapshots, while GitHub acts as the cloud remote where those snapshots are backed up and shared. Using branches allows developers to build features or fix bugs in isolation before merging tested changes into `main`, and keeping commits scoped to one mission at a time makes the history easy to audit.

## Difficulties Faced
Earlier in the setup, my local repository started on `master` instead of `main`, and pasting a truncated remote URL caused `git push` to fail until I fixed the remote link.

## How I Resolved Them
Renamed the branch with `git branch -M main`, verified the exact remote URL using `git remote -v`, and checked `git status` before every commit so only the intended mission folder was staged.

## Evidence / Files
* `mission-06-git-github/README.md`
* `mission-06-git-github/branch_note.txt`

## Commit Details
* **Commit Message**: `Complete Git and GitHub workflow mission`