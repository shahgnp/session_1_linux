# Lab Title: Linux System Administration & Automation
**Objective:** Learn to chain commands together, manage running processes, and automate repetitive tasks with basic scripting.

---

### Phase 1: The Power of Piping & Redirection
*Goal: Connect small tools to solve complex problems.*

1.  **Piping (`|`):**
    *   *Task:* List everything in the `/etc` directory, but only show lines containing the word "network".
    *   Command: `ls /etc | grep "network"`
2.  **Redirecting Errors:**
    *   *Task:* Try to find a file in a forbidden folder and save the error message to a file.
    *   Command: `ls /root 2> error.log`
    *   Command: `cat error.log`
3.  **Sorting & Uniqueness:**
    *   *Task:* Take a list of names, sort them, and remove duplicates.
    *   Command: `echo -e "Zebra\nApple\nZebra\nBanana" > animals.txt`
    *   Command: `sort animals.txt | uniq`

---

### Phase 2: Process Management
*Goal: Monitor system health and stop "frozen" programs.*

1.  **See what’s running:**
    *   Command: `top` (or `htop` if installed). 
    *   *Task:* Identify which process is using the most CPU (Press `q` to exit).
2.  **Backgrounding a Task:**
    *   Command: `sleep 100 &` 
    *   *Observation:* The `&` lets you keep using the terminal while the command runs.
3.  **Find and Kill a process:**
    *   Command: `ps aux | grep sleep` (Find the Process ID / PID).
    *   Command: `kill [PID_NUMBER]` (Replace with the actual ID found).
4.  **System Resources:**
    *   Command: `df -h` (Check disk space in "human-readable" format).
    *   Command: `free -m` (Check RAM usage).

---

### Phase 3: Advanced Searching & Permissions
*Goal: Find needles in haystacks and manage user access.*

1.  **The `find` command:**
    *   *Task:* Find all files in the system ending in `.log`.
    *   Command: `find . -name "*.log"`
2.  **Superuser Powers (`sudo`):**
    *   *Task:* Update the system package list (requires root).
    *   Command: `sudo apt update` (On Ubuntu/Debian).
3.  **Ownership:**
    *   Command: `ls -l error.log`
    *   *Task:* See who "owns" the file (usually the user).
    *   *Concept:* `chown` is used to change owners, but we will stick to `chmod` for safety in this lab.

---

### Phase 4: Basic Scripting & Automation
*Goal: Create a "program" to do your work for you.*

1.  **Create a script file:**
    *   Command: `nano backup.sh`
2.  **Write the script:** (Type the following into the editor):
    ```bash
    #!/bin/bash
    echo "Starting backup..."
    mkdir -p ~/my_backup
    cp -r ~/lab_work ~/my_backup
    echo "Backup completed at $(date)"
    ```
    *(Press Ctrl+O, Enter, then Ctrl+X to save and exit)*.
3.  **Make it executable:**
    *   Command: `chmod +x backup.sh`
4.  **Run it:**
    *   Command: `./backup.sh`