# OverTheWire Bandit: Level 1 to Level 2 Writeup

## 1. Executive Summary
* **Target:** Bandit Level 1
* **Objective:** Extract the password for the next level (`bandit2`) from a file named `-` located in the home directory.
* **Target File:** `~/-`

## 2. Technical Concepts and Utilities
* **Relative Pathing (`./`):** A way to tell Linux to look explicitly inside your current folder. It helps prevent the terminal from confusing unusual filenames with command options.
* **Standard Input (`stdin`):** The default way a command receives text. In Linux, a single dash (`-`) is a built-in shortcut that tells a command to wait for you to type text into the terminal instead of opening a file.
* **cat (Concatenate):** A command used to open a file and read its contents on the screen.

## 3. Methodology and Execution

### Step 1: Host Authentication
Connected to the OverTheWire server using the `bandit1` username and the password found in the previous challenge:
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
### Step 2: Directory Enumeration
Listed the files in the home directory to find the target file using the `ls` command:

**Output:** `-`

### Step 3: File Type Verification
Because the filename is just a dash (-), the file command was run using relative pathing (./-) so Linux wouldn't get confused by the special character:
``` file ./-```

**Output:** `./- : ASCII text`
The output confirmed that - is a plain text file and is safe to open.

## Step 4: Credential Extraction
Opened and read the contents of the file by adding ./ in front of the dash to safely bypass the shortcut and print the password:
`cat ./-`

**Output:** `[REDACTED]`

### 4. Key Takeaways and Defensive Relevance
1. Handling strange filenames: Attackers or misconfigured scripts sometimes create files with strange names(like starting with dashes or spaces) to break automated security tools.
Knowing how to use path boundaries like `./` ensures your tools can always read them
2. Understanding input streams: The single dash `-` is a powerful shortcut used across many Linux tools to pipe text around. Recognizing when a symbol is a file name versus a system command is a foundational skill in Linux administration.

