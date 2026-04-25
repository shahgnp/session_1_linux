# Lab Title: Linux Terminal Foundations
**Objective:** Master the core commands needed to navigate the filesystem, manage files, and search for data.

---

### Phase 1: Orientation & Navigation
*Goal: Understand where you are and how to move around.*

1.  **Check your location:**
    *   Command: `pwd` (Print Working Directory)
    *   *Task:* Confirm you are in your "home" directory (usually `/home/username`).
2.  **List what’s inside:**
    *   Command: `ls`
    *   Command: `ls -l` (Long format: shows sizes and dates)
    *   Command: `ls -a` (Show hidden files starting with a dot `.`)
3.  **Move around:**
    *   Command: `cd /tmp` (Go to the temporary folder)
    *   Command: `cd ..` (Go up one level)
    *   Command: `cd ~` (Go back to your home directory)

---

### Phase 2: File & Directory Creation
*Goal: Create a workspace for a fictional project.*

1.  **Create a folder structure:**
    *   Command: `mkdir -p lab_work/data`
    *   *Task:* Create a folder named `lab_work` with a subfolder named `data`.
2.  **Create empty files:**
    *   Command: `touch lab_work/note1.txt lab_work/note2.txt`
3.  **Move and Rename:**
    *   Command: `mv lab_work/note2.txt lab_work/data/secret.txt`
    *   *Task:* Move `note2.txt` into the `data` folder and rename it to `secret.txt`.
4.  **Copy files:**
    *   Command: `cp lab_work/note1.txt lab_work/note1_backup.txt`

---

### Phase 3: Content Manipulation
*Goal: Learn to read and write data without using a mouse.*

1.  **Write to a file:**
    *   Command: `echo "Linux is powerful" > lab_work/note1.txt`
2.  **Append to a file:**
    *   Command: `echo "I am learning the terminal" >> lab_work/note1.txt`
3.  **Read the file:**
    *   Command: `cat lab_work/note1.txt`
4.  **The "Search" Power (Grep):**
    *   *Task:* Search for the word "Linux" in your file.
    *   Command: `grep "Linux" lab_work/note1.txt`
5.  **Reading Large Files (Head/Tail):**
    *   Command: `head -n 1 lab_work/note1.txt` (See only the first line).

---

### Phase 4: Permissions & Cleanup
*Goal: Understand security and how to delete items.*

1.  **Check Permissions:**
    *   Command: `ls -l lab_work/note1.txt`
    *   *Observation:* Look at the `rwx` strings at the start of the line.
2.  **Change Permissions:**
    *   Command: `chmod 400 lab_work/note1.txt` (Make it read-only).
    *   *Task:* Try to `echo "test" > lab_work/note1.txt`. It should fail (Permission denied).
3.  **The Delete Command:**
    *   Command: `rm lab_work/note1_backup.txt`
    *   Command: `rm -rf lab_work` (Careful! This deletes the folder and everything inside it).

---

### Phase 5: Review & Shortcuts
*Goal: Efficiency tips.*

1.  **History:** Type `history` to see every command you ran today.
2.  **The Tab Key:** Start typing a filename and hit `Tab` to auto-complete it (This is the most important skill in Linux!).
3.  **Clear:** Type `clear` to clean your screen.

---

### Quick Reference Sheet (Cheat Sheet)

| Command | Action |
| :--- | :--- |
| `pwd` | Where am I? |
| `ls` | List files |
| `cd` | Change directory |
| `mkdir` | Make directory |
| `touch` | Create empty file |
| `cp` | Copy |
| `mv` | Move / Rename |
| `rm` | Remove (Delete) |
| `cat` | View file content |
| `grep` | Search for text |
| `man <cmd>` | Help (Manual) for any command |

---

### Instructor Notes for Success:
*   **Common Pitfall:** Remind students that Linux is **case-sensitive** (`Folder` is not the same as `folder`).
*   **The "Escape" Key:** If a student gets stuck inside a command, tell them to press `Ctrl + C` to kill the process and return to the prompt.
*   **Environment:** This lab works on any Ubuntu, Debian, CentOS, or macOS Terminal. For Windows users, recommend **WSL2** or **Git Bash**.