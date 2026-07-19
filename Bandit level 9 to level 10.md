## Level 9 → Level 10

**Objective:** Retrieve the password for Level 10 from the file `data.txt` by finding one of the few human-readable strings, which is preceded by several `=` characters.

### Concepts Covered
* **Extracting Printable Strings (`strings`):** Scanning a binary or non-text file to filter out the corrupted data and pull out only the actual text characters.
* **Pattern Matching with Context:** Using `grep` to look for structural patterns (like a sequence of equal signs `==`) rather than a specific word.

---

### Step-by-Step Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit9` and the port `2220`.

**Command:**
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

## Step 2: Test Reading the File Normally
If you inspect the file type or try to use a standard text tool like cat, you will see why this level is different.

**Command:**
`file data.txt`

**Output:**
data.txt: data

## Step 3: Filter out Binary Noise and Grab the Password
Because the password is hidden inside a binary file, we use the strings command. This tool strips away all the unreadable binary data and prints only the printable lines of text. 
We then pipe (|) that clean text into grep to find the line containing the = characters.

**Command:**
`strings data.txt | grep "=="`

**Output:**
========== [Hidden_Password]--> This will be the password for level 10
