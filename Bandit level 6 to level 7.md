## Level 6 → Level 7

**Objective:** Retrieve the password for Level 7 from a file hidden somewhere on the server that matches all of the following system properties:
* Owned by user `bandit7`
* Owned by group `bandit6`
* Exactly 33 bytes in size

### Concepts Covered
* **System-Wide Searching:** Using `find /` to scan the entire operating system from the root directory instead of just the current folder.
* **Ownership Filtering:** Using `-user` and `-group` flags to isolate files based on Linux permission configurations.
* **Error Redirection (`2>/dev/null`):** Suppressing standard error messages (like "Permission denied") so they do not clutter your terminal screen.

---

### Step-by-Step Walkthrough (With Output)

### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit6` and the port `2220`.

**Command:**
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

### Step 2: Search the Server for the File
Because the file could be absolutely anywhere on the server, we must search starting from the root directory (/). We will combine the target size, user ownership, and group ownership parameters.

**Command:** 

`find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`

**Output:**

/var/lib/dpkg/info/bandit7.password

### Step 3: Read the Target File
Now that the exact system path has been uncovered, pass it straight to the cat command to reveal the key.

**Command:**

`cat /var/lib/dpkg/info/bandit7.password`

**Output:**

[Hidden_Password]<-- (This will be your actual Level 7 password)
