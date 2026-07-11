
### OverTheWire Bandit: Level 0 to Level 1 Writeup

### 1. Executive Summary
* **Target:** Bandit Level 0
* **Objective:** Log into the remote server using SSH and find the password for the next level (`bandit1`).
* **Target File:** `~/readme`

## 2. Technical Concepts and Utilities
* **SSH (Secure Shell):** A secure way to log into a remote computer's terminal over the internet.
* **ls (List):** A command used to list all the files and folders in your current directory.
* **file:** A command that inspects a file to tell you what type of data it contains (like text, code, or a picture).
* **cat (Concatenate):** A command used to open a file and read its contents directly on the screen.

## 3. Methodology and Execution

### Step 1: Host Authentication
Connected to the OverTheWire server using the provided Level 0 username and password on port 2220:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
