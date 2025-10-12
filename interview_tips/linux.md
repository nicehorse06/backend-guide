## 🐧 Linux

> There's a lot to learn here, and I'm still exploring.  
> Focus on understanding **what each command reveals**, not just syntax memorization.

---

### 🧩 System Information
- **Kernel Version**
  ```bash
  uname -r
  ```
  → Check Linux kernel version (useful for module compatibility).

- **Distribution Info**
  ```bash
  cat /etc/os-release
  lsb_release -a
  ```
  → View OS distribution and version.

- **Hardware / CPU Info**
  ```bash
  lscpu          # CPU cores, threads, cache
  cat /proc/cpuinfo
  ```

- **Memory Info**
  ```bash
  free -h        # Total, used, swap
  cat /proc/meminfo
  ```

- **Disk Info**
  ```bash
  df -h          # Disk usage summary by mount point
  du -sh /var/*  # Directory-level usage
  lsblk          # Show block devices and mount points
  ```

- **System Uptime**
  ```bash
  uptime
  who -b         # Last system boot time
  ```

---

### ⚙️ Process & Resource Monitoring
- **Process List**
  ```bash
  ps aux         # All processes
  ps -ef         # Full-format listing
  top / htop     # Real-time CPU, memory, process info
  ```
  → Interview Tip: Know how to find the process consuming most CPU or memory.

- **Detailed File Stats**
  ```bash
  stat filename
  ```

- **Kill a Process**
  ```bash
  kill PID
  kill -9 PID          # SIGKILL (force)
  pkill process_name   # Kill by name
  killall nginx        # Kill all by name
  ```

- **Signals**
  ```bash
  kill -l       # List all signals
  ```
  - `SIGTERM` (15): Graceful stop  
  - `SIGKILL` (9): Force terminate  
  - `SIGHUP`: Reload config  
  - `SIGINT`: Interrupt (Ctrl+C)

- **Zombie Process**
  - Process completed but parent hasn’t read exit status.  
  - Appears in `ps` as `<defunct>`.
  - Fix by ensuring parent handles `wait()`.

- **Process Hierarchy**
  ```bash
  ps -eo pid,ppid,pgid,sid,comm
  ```
  - **PID** = Process ID  
  - **PPID** = Parent Process ID  
  - **PGID** = Process Group ID  
  - **SID** = Session ID  
  - **PID 1**: Init/systemd — ancestor of all processes.

---

### ⚡ Performance & Diagnostics
- **CPU & Memory**
  ```bash
  top / htop            # Real-time resource usage
  vmstat 1              # Processes, memory, swap, I/O
  iostat -xz 1          # I/O performance
  mpstat -P ALL 1       # Per-core CPU stats
  ```
  → Interview Tip: Explain “load average” and “I/O wait”.

- **System Performance Analysis**
  ```bash
  sar -u 1 3            # Historical CPU stats
  pidstat 1             # Per-process performance
  ```
  - Use `strace -p PID` to trace system calls (debug I/O hangs).
  - `lsof -p PID` → list open files by process.

---

### 🔒 File Permissions & Ownership
- **Permissions**
  ```bash
  chmod 755 script.sh   # rwxr-xr-x
  ```
  - **r (4)** = read, **w (2)** = write, **x (1)** = execute.

- **Ownership**
  ```bash
  chown user:group file.txt
  ```

- **Links**
  ```bash
  ln file.txt link.txt         # Hard link
  ln -s /path/original link    # Symbolic link
  ```

---

### 📦 Package Management
- **APT / DPKG**
  ```bash
  sudo apt update && sudo apt upgrade
  sudo apt install nginx
  dpkg -l | grep nginx         # List installed packages
  dpkg -L nginx                # Files installed by package
  ```
  → Interview Tip: Explain difference between `apt` (high-level) and `dpkg` (low-level).

---

### 🕹️ Bash Basics
- **Command History**
  - `!!` → Repeat last command  
  - `!n` → Repeat nth command  
  - `!grep` → Repeat last command starting with "grep"

- **Operators**
  - `&&`: Run next command only if previous succeeded.  
  - `||`: Run next command only if previous failed.

- **Redirection**
  ```bash
  cmd > out.txt 2>&1          # Redirect stdout + stderr
  grep "pattern" file > out   # Output to file
  find / -name "*.log" > /dev/null 2>&1
  ```

- **Common Utilities**
  ```bash
  sort file.txt
  grep "pattern" file.txt
  awk '{print $1,$3}'
  sed 's/foo/bar/g'
  cut -d':' -f1 /etc/passwd
  wc -l file.txt
  ```

---

### 🧱 Logs & System Events
- **View Logs**
  ```bash
  tail -f /var/log/syslog
  journalctl -xe            # View systemd logs
  journalctl -u nginx       # Logs for a specific service
  ```

- **Login Logs**
  ```bash
  last                      # Recent logins
  who                       # Logged-in users
  w                         # Who + activity summary
  ```

- **Kernel Messages**
  ```bash
  dmesg | tail
  ```

---

### ⚙️ Services & Scheduling
- **Systemctl (systemd)**
  ```bash
  sudo systemctl start nginx
  sudo systemctl stop nginx
  sudo systemctl restart nginx
  sudo systemctl status nginx
  sudo systemctl enable nginx   # Start on boot
  sudo systemctl disable nginx
  ```

- **Cron Jobs**
  ```bash
  crontab -e
  crontab -l
  ```
  Example entry:
  ```
  */10 * * * * /usr/local/bin/backup.sh
  ```
  → Runs every 10 minutes.

---

### 🌐 Networking
- **IP & Interfaces**
  ```bash
  ip addr show
  ifconfig
  ip link set eth0 up/down
  ```
  → `ip` is modern replacement for `ifconfig`.

- **Ping & Connectivity**
  ```bash
  ping -c 4 google.com
  traceroute 8.8.8.8
  ```

- **Routing**
  ```bash
  route -n
  ip route show
  ```

- **Check Port Usage**
  ```bash
  netstat -tulnp | grep 8080
  ss -tulnp | grep 8080        # Modern alternative
  lsof -i :8080
  ```

- **Packet Capture**
  ```bash
  sudo tcpdump -i eth0 port 80 -nn
  sudo tcpdump -w capture.pcap
  ```
  → Explain filters and how to use Wireshark for analysis.

- **Firewall**
  ```bash
  sudo iptables -L
  sudo ufw status
  sudo ufw allow 22/tcp
  ```

---

### 💾 Storage & Filesystems
- **Mount / Unmount**
  ```bash
  mount /dev/sdb1 /mnt/data
  umount /mnt/data
  ```
  → Interview Tip: explain mount points and fstab entries.

- **Swap**
  ```bash
  swapon -s
  sudo swapon /swapfile
  sudo swapoff /swapfile
  ```
  - Used when physical memory is full.
  - Slower than RAM; avoid high swap usage in production.

---

### 🧠 Kernel & Modules
- **Kernel Messages**
  ```bash
  dmesg | less
  ```

- **Modules**
  ```bash
  lsmod              # List loaded modules
  insmod module.ko   # Insert module
  modprobe module    # Load with dependencies
  rmmod module       # Remove module
  ```

---

### 🔍 System Debug & Troubleshooting
- **Check Running Services**
  ```bash
  systemctl list-units --type=service --state=running
  ```

- **Open Files by Process**
  ```bash
  lsof -p PID
  ```

- **Check File Descriptors**
  ```bash
  ulimit -n
  ```

- **Monitor File Access**
  ```bash
  lsof /var/log/syslog
  ```

- **Find Large Files**
  ```bash
  find / -type f -size +500M
  ```

- **Search for Patterns**
  ```bash
  grep -R "error" /var/log/
  ```

---

### ⚡ Common Interview Questions
- Explain difference between **process**, **thread**, and **coroutine** in Linux.
- How do you check which process is using port 8080?
- What is the difference between **SIGTERM** and **SIGKILL**?
- What happens when you run `kill -9 1`?
- How do you find and kill a zombie process?
- How do you view real-time logs for a service?
- How do you check CPU/memory/disk bottlenecks?
- What’s the difference between `systemctl` and `service`?
- How do you schedule a job every 5 minutes?
- Explain `2>&1` in Bash.
- How do you trace which system calls a process is making?  
  → `strace -p PID`
- How do you debug a slow network connection?  
  → Use `ping`, `traceroute`, `tcpdump`, and `ss`.

---

### ⚡ Quick Summary
> Linux mastery = **knowing how to observe and diagnose.**  
> Remember:  
> - `ps/top` → Processes  
> - `df/du` → Disk  
> - `free/vmstat` → Memory  
> - `netstat/ss/tcpdump` → Network  
> - `systemctl/journalctl` → Services & Logs  
> - `grep/find/awk/sed` → Text processing  
> - `cron` → Scheduling  
> - `chmod/chown` → Permissions  
> Learn patterns, not just commands — that’s what interviewers look for.
