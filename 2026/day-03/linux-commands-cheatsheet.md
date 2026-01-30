Process Management Commands
| Command          | One-line usage                           |
| ---------------- | ---------------------------------------- |
|  ps aux          | Show all running processes with details  |
|  top             | Real-time view of CPU & memory usage     |
|  htop            | User-friendly interactive process viewer |
|  pidof process   | Get PID of a running process             |
|  kill PID        | Terminate a process by PID               |
|  kill -9 PID     | Force kill an unresponsive process       |
|  pkill name      | Kill process by name                     |
|  bg              | Resume a stopped job in background       |
|  fg              | Bring background job to foreground       |
|  jobs            | List jobs started in current shell       |
|  nice -n 10 cmd  | Start process with priority              |
|  uptime          | Show system running time & load          |


File System Commands

| Command                 | One-line usage                     |
| ----------------------- | ---------------------------------- |
|  ls -lh                 | List files with size & permissions |
|  pwd                    | Show current directory path        |
|  cd dir                 | Change directory                   |
|  du -sh dir             | Show directory size                |
|  df -h                  | Show disk space usage              |
|  stat file              | Detailed file information          |
|  find /path -name file  | Search file by name                |
|  chmod 755 file         | Change file permissions            |
|  chown user:group file  | Change file owner                  |
|  mount                  | Show mounted file systems          |
|  umount /mnt            | Unmount a file system              |


Networking & Troubleshooting Commands

| Command                 | One-line usage                 |
| ----------------------- | ------------------------------ |
|  ping google.com        | Check network connectivity     |
|  ip addr                | Show IP addresses & interfaces |
|  ip route               | Display routing table          |
|  ss -tuln               | Show listening ports           |
|  netstat -tulnp         | Network connections & ports    |
|  curl url               | Test HTTP/API response         |
|  dig domain.com         | DNS lookup                     |
|  traceroute domain.com  | Trace network path             |
|  nslookup domain.com    | Query DNS server               |
|  hostname -I            | Show system IP address         |
