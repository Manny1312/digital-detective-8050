# Mission 0 — Environment Setup & Repository Initialization

## Task
Set up my local development environment on macOS, verify Python and Git installations, build the folder structure for all nine missions, and push the initial project to a public GitHub repository.

## Work Completed
* Created the main project directory `digital-detective-8050` along with individual folders from `mission-00-setup` through `mission-08-final-report`.
* Added initial `README.md` files inside every mission folder and created `number_converter.py` inside `mission-05-numbers-data/`.
* Added a `.gitignore` file to prevent macOS `.DS_Store` metadata files from being tracked or uploaded.
* Initialized a local Git repository, renamed the default branch to `main`, and linked it to my remote GitHub repository.
* Updated the root [README.md](../README.md) with the project overview and clickable Mission Index links.

## Commands / Tools Used
* **Tools**: macOS Terminal, Visual Studio Code, Git, Python 3, GitHub
* **Environment Versions** *(verify yours in terminal)*:
  * Python: `Python 3.x.x` *(run `python3 --version`)*
  * Git: `git version 2.x.x` *(run `git --version`)*
* **Key Commands Run**:
  ```bash
  mkdir -p mission-00-setup mission-01-computer-basics mission-02-terminal mission-03-operating-system mission-04-programs mission-05-numbers-data mission-06-git-github mission-07-networking mission-08-final-report
  echo ".DS_Store" > .gitignore
  git init
  git branch -M main
  git add .
  git commit -m "Set up Digital Detective mission structure"
  git remote add origin https://github.com
  git push -u origin main
  ```

## My Understanding
A **Git repository** is a tracked project folder that records snapshots (commits) of every change made over time. Hosting that repository on **GitHub** creates an online remote backup and makes it possible to organize and submit each mission cleanly as separate commits.

## Difficulties Faced
* Git initially created the local branch as `master` instead of `main`.
* When adding the remote origin URL, a formatting/copy-paste issue cut the repository link short (`https://github.com`), causing `git push` to fail with a `repository not found` error.
* GitHub had created a default initial commit when I made the repository online, which blocked a standard push.

## How I Resolved Them
* Renamed the local branch to `main` using `git branch -M main`.
* Copied the exact HTTPS URL directly from the green **Code** button on GitHub and updated the remote using `git remote set-url origin`.
* Pushed my local setup cleanly using `git push -u origin main --force`.

## Evidence / Files
* [Root Project README](../README.md)
* [`.gitignore`](../.gitignore)
* `mission-00-setup/README.md` (this file)
* Next Mission: [Mission 1 — Computer Basics](../mission-01-computer-basics/README.md)

## Commit Details
* **Repository Name**: `digital-detective-8050`
* **Visibility**: Public
* **Initial Commit Message**: `Set up Digital Detective mission structure`
