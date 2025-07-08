**Linux process management commands** clearly and with examples. These are essential for monitoring, managing, and controlling processes on a Linux system.

---

# 📖 Linux Process Management Commands

---

## 📌 View Running Processes

| Command | Description                                              | Example         |
| :------ | :------------------------------------------------------- | :-------------- |
| `ps`    | View current running processes for the current user.     | `ps aux`        |
| `top`   | Real-time system summary and process list.               | `top`           |
| `htop`  | Enhanced `top` (if installed) with color and navigation. | `htop`          |
| `pidof` | Get the Process ID (PID) of a running program.           | `pidof nginx`   |
| `pgrep` | Search for processes by name.                            | `pgrep apache2` |

sudo yum install htop -y
htop --version 

sudo yum install httpd 
sudo systemctl start httpd 
suod systemctl enable httpd 
pidof httpd

---

## 📌 Start/Stop Processes

| Command                       | Description                                     | Example                          |
| :---------------------------- | :---------------------------------------------- | :------------------------------- |
| `systemctl start <service>`   | Start a service (on systemd systems).           | `sudo systemctl start nginx`     |
| `systemctl stop <service>`    | Stop a service.                                 | `sudo systemctl stop nginx`      |
| `systemctl restart <service>` | Restart a service.                              | `sudo systemctl restart apache2` |
| `nohup <command> &`           | Run a command in background, immune to hangups. | `nohup python app.py &`          |

---

## 📌 Kill Processes

| Command             | Description                      | Example         |
| :------------------ | :------------------------------- | :-------------- |
| `kill <PID>`        | Kill a process by PID.           | `kill 1234`     |
| `killall <process>` | Kill all instances of a process. | `killall nginx` |
| `kill -9 <PID>`     | Forcefully kill a process.       | `kill -9 1234`  |
| `pkill <pattern>`   | Kill processes by name pattern.  | `pkill apache2` |

---

## 📌 Process Priority Control

| Command                        | Description                                             | Example                 |
| :----------------------------- | :------------------------------------------------------ | :---------------------- |
| `nice -n <priority> <command>` | Start a process with priority (-20 highest, 19 lowest). | `nice -n 5 myscript.sh` |
| `renice <priority> <PID>`      | Change priority of a running process.                   | `renice 10 1234`        |

---

## 📌 Background & Foreground Control

| Command            | Description                             | Example      |
| :----------------- | :-------------------------------------- | :----------- |
| `<command> &`      | Run command in background.              | `sleep 60 &` |
| `jobs`             | List background jobs.                   | `jobs`       |
| `fg %<job_number>` | Bring background job to foreground.     | `fg %1`      |
| `bg %<job_number>` | Resume a stopped job in the background. | `bg %1`      |

---

## 📌 Monitoring Resource Usage

| Command   | Description                                 | Example    |
| :-------- | :------------------------------------------ | :--------- |
| `top`     | Real-time CPU, memory usage.                | `top`      |
| `htop`    | Graphical top-like utility (needs install). | `htop`     |
| `vmstat`  | Memory, CPU, IO stats.                      | `vmstat 5` |
| `iostat`  | Disk IO statistics.                         | `iostat`   |
| `free -m` | Display memory usage.                       | `free -m`  |

---

## 📌 Process Tree & Hierarchy

| Command  | Description                    | Example  |
| :------- | :----------------------------- | :------- |
| `pstree` | Show processes in tree format. | `pstree` |

---

## 📌 Example Session:

```bash
# List all running processes
ps aux

# View real-time process stats
top

# Kill a process with PID 4567
kill 4567

# Start nginx service
sudo systemctl start nginx

# Run a script in background
./myscript.sh &

# Check running jobs
jobs

# Bring job number 1 to foreground
fg %1
```

---

## 📦 Install htop and iostat (if not present)

```bash
sudo apt install htop sysstat  # For Debian/Ubuntu
sudo yum install htop sysstat  # For RHEL/CentOS
```
