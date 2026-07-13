# OverTheWire: Bandit Walkthroughs

## Level 2 → Level 3
**Objective:** Retrieve the password for the next level from a file called `spaces in this filename` located in the home directory.

### Concept Covered
* **Handling Spaces in Filenames:** By default, Linux uses spaces to separate arguments/commands. If a filename has spaces, the shell will treat each word as a different file unless you explicitly group them.

### Solution Steps
1. **Connect to the server:**
   ```bash
   ssh bandit2@bandit.labs.overthewire.org -p 2220
2. **List the directory content to verify the filename:**
`ls`
*Output:* `spaces in the filename`
