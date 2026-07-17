## Level 4 → Level 5

**Objective:** Retrieve the password for Level 5 from the only human-readable file located inside the `inhere` directory.

### Concepts Covered
* **Determining File Types:** Using the `file` command to look at a file's underlying encoding format.
* **Wildcards (`*`):** A shortcut character used to represent any number of characters in a file or directory name.
* **ASCII Text vs Data:** Standard text documents are labeled as `ASCII text` (human-readable), while compiled or binary files appear as `data`.

---

### Step-by-Step Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit4` and the port `2220`.

**Command:**
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

### Step 2: Move into the Target Directory and Inspect Contents
Change directories into the inhere folder and check what is inside.

**Commands:**
`cd inhere`
`ls`

**Output:**

-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09


