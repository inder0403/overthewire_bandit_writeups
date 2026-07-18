## Level 7 → Level 8

**Objective:** Retrieve the password for Level 8 from the file `data.txt`, located next to the word "millionth".

### Concepts Covered
* **Searching Inside Files:** Using the `grep` command to look for specific text strings or patterns within a file.
* **Pipelining (`|`):** Directing the output of one command to serve as the input for another command.
* **Handling Massive Files:** Avoiding opening massive files manually by leveraging automated text filters.

---

### Step-by-Step** Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit7` and the port `2220`.

**Command:**
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
## Step 2: Inspect the Target File
Check the current directory to confirm data.txt is present.

**Commands:**
`ls -lh data.txt`

**Output:**
-rw-r----- 1 bandit8 bandit7 4.1M Jul 18 17:15 data.txt

## Step 3: Extract the Password using grep
Instead of printing out the entire file, we will use grep (Global Regular Expression Print) to filter the file and only show lines that contain the exact word "millionth".

**Command:**
`grep "millionth" data.txt`

**Output:**
millionth                           [Hidden_Password]

## Step 4: Alternative Method (Using a Pipe)
You can achieve the exact same result by reading the file with cat and "piping" the massive text stream directly into grep.

**Command:**

`cat data.txt | grep "millionth"`

**Output:**

millionth                           [Hidden_Password]  <-- (This will be your actual Level 8 password)
