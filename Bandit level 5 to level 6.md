## Level 5 → Level 6

**Objective:** Retrieve the password for Level 6 from a file somewhere under the `inhere` directory that matches all of the following properties:
* Human-readable
* 1033 bytes in size
* Not executable

### Concepts Covered
* **Advanced Searching with `find`:** Searching recursively through multiple directories using specific criteria.
* **Filtering by Size:** Using the `-size` flag with `c` (which stands for bytes).
* **Logical Negation (`!`):** Excluding specific properties (like executables) from search results.
* **Specifying File Type:** Using `-type f` to look only for regular files (excluding directories).

---

### Step-by-Step Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit5` and the port `2220`.

**Command:**
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

### Step 2: Navigate and Inspect the Directory
Check the contents of the inhere directory.

**Command:**

`cd inhere`
`ls`

**Output:**
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17

### Step 3: Find the File Matching the Criteria
We will use the powerful find command inside the inhere directory. We need to filter by file type (files only), exact size (1033 bytes), and check that it is not an executable.

**Command:**

`find . -type f -size 1033c ! -executable`

**Output:**

./maybehere07/.file2

## Step 4: Read the Target File
Now that we have the exact relative path to the correct file, we can read it using cat.

**Command:**
cat ./maybehere07/.file2

**Output:**
[Hidden_Password]- This will be the password for Level 6
