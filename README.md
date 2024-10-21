As a DevOps engineer, having a strong grasp of Linux commands is crucial for system administration, automation, troubleshooting, and configuring servers. Here is a comprehensive set of Linux commands that you need to master, categorized based on their use cases:

### 1. **File and Directory Management**
   - **`ls`**: List files and directories.
     ```bash
     ls -l     # Long listing format
     ls -a     # List all, including hidden files
     ```
   - **`cd`**: Change directory.
     ```bash
     cd /path/to/directory
     cd ~      # Go to home directory
     ```
   - **`pwd`**: Print working directory (current location).
     ```bash
     pwd
     ```
   - **`mkdir`**: Create directories.
     ```bash
     mkdir new_dir
     mkdir -p /path/to/new_dir  # Create parent directories if they don’t exist
     ```
   - **`rm`**: Remove files or directories.
     ```bash
     rm file.txt
     rm -rf /path/to/directory  # Remove directory and its contents recursively
     ```
   - **`cp`**: Copy files and directories.
     ```bash
     cp file.txt /new/path/
     cp -r /path/to/source /path/to/destination  # Copy directories recursively
     ```
   - **`mv`**: Move or rename files and directories.
     ```bash
     mv oldfile.txt newfile.txt
     mv /path/to/file /new/path/
     ```

### 2. **File Permissions and Ownership**
   - **`chmod`**: Change file permissions.
     ```bash
     chmod 755 file.sh  # Owner can read/write/execute, others can read/execute
     chmod +x file.sh   # Make file executable
     ```
   - **`chown`**: Change file ownership.
     ```bash
     chown user:group file.txt  # Change ownership of file
     chown -R user:group /path  # Change ownership recursively
     ```
   - **`chgrp`**: Change group ownership.
     ```bash
     chgrp group_name file.txt
     ```

### 3. **Process Management**
   - **`ps`**: Display current running processes.
     ```bash
     ps aux         # Show all running processes
     ps -ef | grep process_name  # Find a specific process
     ```
   - **`top`**: Real-time process monitoring.
     ```bash
     top  # View system processes and resource usage
     ```
   - **`htop`**: Enhanced version of `top` (if installed).
   - **`kill`**: Terminate processes by PID.
     ```bash
     kill PID  # Send termination signal to a process
     kill -9 PID  # Force kill a process
     ```
   - **`pkill`**: Kill processes by name.
     ```bash
     pkill -f process_name
     ```

### 4. **Disk and Filesystem Management**
   - **`df`**: Show disk space usage.
     ```bash
     df -h   # Human-readable format
     ```
   - **`du`**: Estimate file and directory space usage.
     ```bash
     du -sh /path/to/directory  # Show total size of a directory
     ```
   - **`mount`**: Mount a filesystem.
     ```bash
     mount /dev/sdb1 /mnt  # Mount a device to a directory
     ```
   - **`umount`**: Unmount a filesystem.
     ```bash
     umount /mnt
     ```

### 5. **User and Group Management**
   - **`useradd`**: Add a new user.
     ```bash
     useradd username
     ```
   - **`passwd`**: Set or change a user’s password.
     ```bash
     passwd username
     ```
   - **`userdel`**: Delete a user.
     ```bash
     userdel -r username  # Remove the user and their home directory
     ```
   - **`groupadd`**: Create a new group.
     ```bash
     groupadd groupname
     ```
   - **`usermod`**: Modify a user account.
     ```bash
     usermod -aG groupname username  # Add user to a group
     ```

### 6. **Network Commands**
   - **`ip` / `ifconfig`**: Display or configure network interfaces.
     ```bash
     ip addr show        # Show IP addresses
     ifconfig            # Deprecated, but still used in older systems
     ```
   - **`ping`**: Test network connectivity.
     ```bash
     ping google.com
     ```
   - **`netstat`**: Network statistics and connections (or `ss` for newer systems).
     ```bash
     netstat -tuln  # List all listening ports
     ss -tuln       # More efficient alternative
     ```
   - **`curl`**: Transfer data from or to a server.
     ```bash
     curl http://example.com  # Fetch content of a webpage
     curl -I http://example.com  # Fetch HTTP headers
     ```
   - **`wget`**: Download files from the web.
     ```bash
     wget http://example.com/file.zip
     ```

### 7. **Package Management (Debian/Ubuntu)**
   - **`apt update`**: Update the list of available packages.
     ```bash
     sudo apt update
     ```
   - **`apt upgrade`**: Install the latest versions of all packages.
     ```bash
     sudo apt upgrade
     ```
   - **`apt install`**: Install a package.
     ```bash
     sudo apt install package_name
     ```
   - **`apt remove`**: Remove a package.
     ```bash
     sudo apt remove package_name
     ```

### 8. **System Monitoring**
   - **`uptime`**: Show how long the system has been running.
     ```bash
     uptime
     ```
   - **`free`**: Display memory usage.
     ```bash
     free -h   # Human-readable format
     ```
   - **`vmstat`**: Report virtual memory statistics.
     ```bash
     vmstat 1  # Display memory, CPU, and I/O stats every second
     ```

### 9. **Search and Filters**
   - **`grep`**: Search for a pattern in files or output.
     ```bash
     grep 'search-term' file.txt
     ps aux | grep nginx  # Find processes related to nginx
     ```
   - **`find`**: Search for files in a directory hierarchy.
     ```bash
     find /path -name "*.log"  # Find files by name
     ```
   - **`locate`**: Find files quickly using a pre-built index.
     ```bash
     locate file_name
     ```

### 10. **Archive and Compression**
   - **`tar`**: Archive and compress files.
     ```bash
     tar -cvf archive.tar /path/to/files   # Create an archive
     tar -xvf archive.tar                  # Extract an archive
     tar -czvf archive.tar.gz /path        # Create a compressed archive
     ```
   - **`gzip`**: Compress files.
     ```bash
     gzip file.txt
     ```

### 11. **Shell Scripting and Automation**
   - **`bash`**: Start a new shell or run a script.
     ```bash
     bash script.sh
     ```
   - **`crontab`**: Schedule jobs to run at specific times.
     ```bash
     crontab -e  # Edit cron jobs
     # Example cron job:
     # Run script every day at midnight
     0 0 * * * /path/to/script.sh
     ```
   - **`systemctl`**: Manage system services (used in `systemd` based systems).
     ```bash
     systemctl start service_name
     systemctl stop service_name
     systemctl restart service_name
     systemctl status service_name
     ```

### 12. **SSH and Remote Management**
   - **`ssh`**: Connect to a remote server via SSH.
     ```bash
     ssh user@remote_host
     ssh user@remote_host -p 2222  # Connect on a custom port
     ```
   - **`scp`**: Securely copy files between hosts.
     ```bash
     scp file.txt user@remote_host:/path/to/destination
     scp -r /local_dir user@remote_host:/remote_dir  # Copy directories
     ```
   - **`rsync`**: Sync files between local and remote systems.
     ```bash
     rsync -avz /local_path user@remote_host:/remote_path
     ```

### 13. **Text Manipulation**
   - **`cat`**: Concatenate and display file content.
     ```bash
     cat file.txt
     ```
   - **`less`**: View file content interactively.
     ```bash
     less file.txt
     ```
   - **`head` / `tail`**: View the beginning or end of a file.
     ```bash
     head -n 10 file.txt  # First 10 lines
     tail -n 10 file.txt  # Last 10 lines
     ```
   - **`awk`**:

14. **Miscellaneous**
- `crontab`: Schedule recurring tasks
  - Example: `crontab -e` (edit cron jobs)
- `alias`: Create shortcuts for commands
  - Example: `alias ll='ls -la'`
- `env`: Display environment variables
- `history`: Show command history
- `whoami`: Display current user
- `hostname`: Display or set system hostname

---

These commands and tools form the backbone of the day-to-day tasks of a DevOps engineer, allowing you to manage infrastructure, automate deployments, troubleshoot issues, and maintain secure environments efficiently.
