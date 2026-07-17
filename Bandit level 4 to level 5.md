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

## Step 3: Find the Human-Readable File
Use the file command combined with a wildcard (*) to check the file type of every single file in the directory at once.

**Command:**

`file ./*`

**Output:**

./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data

## Step 4: Read the Target File
Because the filename begins with a dash (-), simply running cat -file07 will cause Linux to interpret -file07 as a command option. To bypass this, specify the explicit relative path by putting ./ in front of it.

**Command:**
`cat ./-file07`

**Output:**
[Hidden_Password]- This password can be used to log in to Level 5



