# Lab Title: Linux Networking & Connectivity
**Objective:** Understand network interfaces, troubleshoot connectivity, and transfer data between systems.

---

### Phase 1: Network Identification
*Goal: Find your machine's "Address" in the digital world.*

1.  **Find your IP Address:**
    *   Command: `ip addr show` (or `ip a`)
    *   *Task:* Identify your local IP address (usually starts with `192.168.x.x` or `10.x.x.x`). Look for the `inet` line.
2.  **Check your Gateway:**
    *   Command: `ip route`
    *   *Task:* Find the "default via" line. This is the IP of your router.
3.  **Check your Hostname:**
    *   Command: `hostname`
    *   Command: `hostname -i` (Just the IPs).

---

### Phase 2: Connectivity & DNS Troubleshooting
*Goal: Verify if you can reach the outside world.*

1.  **The "Hello" of Networking:**
    *   Command: `ping -c 4 google.com`
    *   *Observation:* Look at the `time=XXms`. This is your latency (lag).
2.  **Trace the Path:**
    *   Command: `traceroute google.com`.
    *   *Task:* See how many "hops" (routers) it takes to reach Google.
3.  **DNS Lookup (The Phonebook):**
    *   Command: `nslookup google.com` (or `dig google.com`).
    *   *Task:* Find the IP address associated with the name "google.com".

---

### Phase 3: Ports & Services
*Goal: See what "Doors" are open on your machine.*

1.  **List Open Ports:**
    *   Command: `ss -tulpn`
    *   *Concept:* Every internet service (Web, SSH, Email) runs on a "Port."
    *   *Task:* Check if any services are currently "Listening."
2.  **Check a Specific Port (Netcat):**
    *   Command: `nc -zv google.com 443`
    *   *Observation:* This checks if Google's web port (443) is open.
3.  **The `/etc/hosts` file:**
    *   Command: `cat /etc/hosts`
    *   *Concept:* This is your local "phonebook" that overrides the internet.

---

### Phase 4: Web Tools & File Transfers
*Goal: Download files and interact with web servers via the CLI.*

1.  **Download a file via CLI:**
    *   Command: `wget https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png`
    *   *Task:* Check if the image appeared in your folder using `ls`.
2.  **Inspect Web Headers (Curl):**
    *   Command: `curl -I https://www.wikipedia.org`
    *   *Observation:* This shows the server info (Type of server, Date, Security headers) without downloading the page.
3.  **Secure Copy (Concept):**
    *   *Task:* Understand how to send a file to another Linux machine.
    *   Command (Instructional): `scp file.txt username@remote_ip:/home/username/` Try sending file from local PC to EC2 instance