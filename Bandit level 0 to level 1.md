
### OverTheWire Bandit: Level 0 to Level 1 Writeup

### 1. Executive Summary
**Target:** Bandit Level 0
**Objective:** Log into the remote server using SSH and find the password for the next level (`bandit1`).
**Target File:** `~/readme`

## 2. Technical Concepts and Utilities
**SSH (Secure Shell):** A secure way to log into a remote computer's terminal over the internet.
**ls (List):** A command used to list all the files and folders in your current directory.
**file:** A command that inspects a file to tell you what type of data it contains (like text, code, or a picture).
**cat (Concatenate):** A command used to open a file and read its contents directly on the screen.

## 3. Methodology and Execution

### Step 1: Host Authentication
Connected to the OverTheWire server using the provided Level 0 username and password on port 2220:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
password entered: bandit0
```
### Step 2: Reconnaissance & locating the password
Upon successful login, I needed to inspect the home directory to find where the level 1 password was stored.
I list the contents of the current working directory using the ```ls``` command

**Output:**   
```readme```
### Step 3: Reading the Flag
The ```readme``` file contains the credential for the next level. I used the ```cat``` utility command to print the file's content:
```
cat readme
```
**Output:** [Bandit1_password]
### Step 4: Verifying the credential and moving to level 1
After copying the retrieved password, I terminated the level 0 session and authenticated as the next user

```exit```

and then
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
I pasted the password obtained from the ```readme``` file  and successfully gained access to the ```bandit1``` account
