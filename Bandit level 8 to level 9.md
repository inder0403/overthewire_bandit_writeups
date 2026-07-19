## Level 8 → Level 9

**Objective:** Retrieve the password for Level 9 from the file `data.txt` by finding the only line of text that occurs exactly once.

### Concepts Covered
* **Sorting Data (`sort`):** Rearranging lines of text alphabetically or numerically. This is required because deduplication commands only work on adjacent lines.
* **Finding Unique Lines (`uniq`):** Filtering out duplicate lines from a text file.
* **Counting Occurrences (`-u` flag):** Instructing `uniq` to isolate and print *only* the lines that are completely unique.
* **Advanced Pipelining (`|`):** Chaining three separate commands together to process a text stream in stages.

---

### Step-by-Step Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit8` and the port `2220`.

**Command:**
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
### Step 2: Inspect the Target File
Check the file properties to see what we are dealing with.

**Commands:** 
`ls -lh data.txt`

**Output:**
-rw-r----- 1 bandit9 bandit8 33K Jul 18 17:15 data.txt

### Step 3: Filter for the Unique Line
The uniq command has a major limitation: it can only compare lines that are right next to each other. To fix this, we must first pass the data through sort. 
Once sorted, all identical lines will group together, allowing uniq -u to successfully strip them away and leave the single unique password.

**Command:**
`sort data.txt | uniq -u`

**Output:**
[Hidden_Password]  <-- (This will be your actual Level 9 password)
