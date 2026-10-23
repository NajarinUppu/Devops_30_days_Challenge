****Linux Basics****
pwd - print working directory

ls - list files

mkdir - create directory

touch - create file

ps - show processes

df - show disk usage

**Practice Commands**
pwd = present working dir
whoami = user name
ls = list
ls -l =list in losng listing format
ls -la = list all hidden files(.) in long list
mkdir devops = create dir
cd devops =change dir
touch file1.txt = create file
touch file2.txt =create file
cp file1.txt backup.txt  = copy file1 to backup
mv file2.txt newfile.txt = move file2 to new
rm backup.txt = remove backup
=======================================================================================================================
**Check System Information**
uname -a    # Displays complete system information (kernel, OS, architecture, hostname, etc.)
hostname    # Shows the system's host/computer name / server name
df -h       # Displays disk space usage of filesystems in human-readable format (GB/MB)  / Monitor disk utilization
free -m     # Shows memory (RAM) and swap usage in MB / check ram and swap mem
uptime      # Shows how long the system has been running, logged-in users, and load average  / Verify server uptime and current load.

**Process Commands**
ps -ef  # Displays all running processes with detailed information such as PID, parent PID, user, start time, and command.

top       # Shows real-time system monitoring including CPU usage, memory usage, load average, and active processes.

ps -ef → "What processes are running?" (Process list snapshot)
top → "How is the server performing right now?" (Live resource monitoring) ctrl+q to stop

===========================================================================================================================
****Linux Administration****
**Users**
whoami- See current user
id - See user details
cat /etc/passwd  - View users

**Permissions**
Create: touch demo.txt
Check permission: ls -l demo.txt
Change permission: chmod 755 demo.txt
Verify: ls -l demo.txt

**Services**
Check SSH service:
        *systemctl status ssh*    or systemctl status sshd
**Logs**
  journalctl -xe
