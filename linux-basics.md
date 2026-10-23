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
ls = Lists files and directories.
ls -l =list in long listing format
       Ex: -rw-r--r-- 1 ubuntu ubuntu 200 Oct 21 notes.txt
Breakdown
-rw-r--r--
│ │  │  │
│ │  │  └ Others permissions
│ │  └ Group permissions
│ └ Owner permissions
└ File type
ls -la = list all hidden files(.) in long list
mkdir devops = create dir
mkdir -p 
mkdir -p project/dev/docker  
project/
└── dev/
    └── docker/
cd devops =change dir
cd .. #Move one level up.
cd ~ #Move to home dir

touch file1.txt = create empty file
touch file2.txt =create file
cp file1.txt backup.txt  = copy file1 to backup
mv file2.txt newfile.txt = move file2 to new
rm backup.txt = remove backup ⚠️ Permanent deletion.
cat file.txt #Display file contents.
rm -rf folder # Delete folder and contents.
rm -rf /  #Dangerous can destroy system

=======================================================================================================================
**Check System Information**
uname -a    # Displays complete system information (kernel, OS, architecture, hostname, etc.)
hostname    # Shows the system's host/computer name / server name
df -h       # Displays disk space usage of filesystems in human-readable format (GB/MB)  / Monitor disk utilization
free -m     # Shows memory (RAM) and swap usage in MB / check ram and swap mem
uptime      # Shows how long the system has been running, logged-in users, and load average  / Verify server uptime and current load.

================================================================================================================================
**Process Commands**
ps  #Shows running processes
ps -ef  # Displays all running processes with detailed information such as PID, parent PID, user, start time, and command.

top       # Shows real-time system monitoring including CPU usage, memory usage, load average, and active processes.

ps -ef → "What processes are running?" (Process list snapshot)
top → "How is the server performing right now?" (Live resource monitoring) ctrl+q to stop

kill 1234 - kill pid  #Terminate process.
kill -9 1234 #Terminate forcefully

============================================================================================================================

**Disk commands**
df -h        # shows disk usage
Example:
       Filesystem Size Used Avail Use%
       /dev/xvda1 20G 8G 12G 40%

du -sh       #Shows folder size.
ex: 1.5G logs

=============================================================================================================================
**Memory Commands**
free -m        # Displays memory in MB
Mem: 2000 1000 1000

=============================================================================================================================
**Network commands**
ping        #Tests connectivity.
ping google.com
nslookup        #Checks DNS resolution.
nslookup google.com
curl        #Send HTTP request.
curl google.com
Testing APIs, applications, health checks.

===========================================================================================================================
****Linux Administration****
**Users**
whoami- See current user
id - See user details 
Show user id and groups
uid=1000(ubuntu)
gid=1000(ubuntu)
useradd  
       sudo useradd devopsuser  - creates new user
       sudo passwd devopsuser - set pasword
       verify user -> cat /etc/passwd | grep devopsuser
       
cat /etc/passwd  - View All users
Interview Question
Where are Linux users stored?  ->/etc/passwd

Switch User -> su - devopsuser

==============================================================================================================================
**Permissions**
Create: touch demo.txt
Check permission: ls -l demo.txt
Change permission: chmod 755 demo.txt
755
Owner = 7 = rwx
Group = 5 = r-x
Others = 5 = r-x
Verify: ls -l demo.txt

chmod +x deploy.sh  #Make script executable.
sudo chown ubuntu:ubuntu file.txt # change ownership
sudo chown devopsuser test.txt

**Groups**
Create Group      #sudo groupadd devops
Verify               #cat /etc/group | grep devops
Add User To Group
       sudo usermod -aG devops devopsuser
       output id devopsuser
       
==============================================================================================================
**Service Management**
Check SSH service:       
        *systemctl status ssh*    or systemctl status sshd
       systemctl status **nginx**   after status service name
       outout :active (running)
*Start service*
       sudo systemctl start nginx
*Stop Service*
       sudo systemctl stop nginx
*Restart*
       sudo systemctl restart nginx
*Enable*    Start service automatically after reboot.
       sudo systemctl enable nginx
**Logs**
  journalctl -xe
