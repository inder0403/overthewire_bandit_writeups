## Level 3 → Level 4

**Objective:** Retrieve the password for Level 4 from a hidden file inside the `inhere` directory.

### Concepts Covered
* **Directory Navigation:** Using `cd` to move into folders and `cd ..` to move backward.
* **Hidden Files:** In Linux, files or folders starting with a dot (`.`) are hidden from standard directory listings.
* **Revealing Hidden Files:** Using the `-a` (all) flag with the `ls` command to see hidden contents.
* **Handling Special Filenames:** Working with filenames that contain leading dots and spaces by wrapping them in quotation marks.

---

### Step-by-Step Walkthrough (With Output)

#### Step 1: Log into the Server
Connect to the Bandit server using the username `bandit3` and the port `2220`.

**Command:**
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

### Step 2: Move into the Target Directory
Use the `cd `(Change Directory) command to move into the inhere folder.

**Command:**
`cd` inhere

### Step 3: Reveal the Hidden File
If you run a normal `ls`, the directory appears empty. To reveal hidden files, append the `-a` flag.

**Command:**
`ls -a`

**Output:**
`.  ..  ... Hiding-From-You`

### Step 4: Read the Hidden File
Because the file name starts with multiple dots and contains a space, you must enclose the entire name in double quotes so the terminal reads it as a single file.

**Command:**
`cat "... Hiding-From-You"`

**Output:**
`[Hidden_Password]`-This password can be used to log in to level 4
