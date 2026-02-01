## Core Components of Linux

## Linux Architecture Diagram

```text
+----------------------+
|        User          |
+----------+-----------+
           |
           v
+----------------------+
| Applications / Shell |
| (ls, ps, top, bash)  |
+----------+-----------+
           |
           v
+----------------------+
|      User Space      |
+----------+-----------+
           |
           | System Calls
           v
+----------------------+
|        Kernel        |
| CPU | Memory | FS    |
| Network | Security  |
+----------+-----------+
           |
           v
+----------------------+
| systemd (PID 1)      |
| Service Manager      |
+----------+-----------+
           |
           v
+----------------------+
| Processes / Services |
| ssh | cron | docker  |
+----------+-----------+
           |
           v
+----------------------+
|       Hardware       |
| CPU | RAM | Disk     |
+----------------------+
```

### Kernel (Heart of Linux)

The kernel is the core component of Linux.
It communicates directly with hardware

Responsible for:
- Process scheduling (decides which process gets CPU)
- management (allocates and frees RAM)
- Device management (disk, network, keyboard)

### User Space

User space is where users and applications operate

Includes:
- Shell (bash)
- Core commands (ls, ps, top)
- Applications and services
  
 User space cannot access hardware directly

 ### init / systemd (System Controller)

- systemd is the first process started by the kernel (PID 1)
- Controls system startup and shutdown
- Manages all services and background processes
- Restarts failed services automatically
- systemd keeps the system stable and available.

## How Processes Are Created & Managed

A process is a program in execution

New processes are created using:
- fork() → creates a child process
- exec() → loads a new program into the process

Kernel assigns:
- PID (Process ID)
- CPU time
- Memory and priority
  
 Process management ensures system performance.

### Process States

- Running (R): Actively using CPU
- Sleeping (S): Waiting for event/input (normal state)
- Stopped (T): Paused by signal or user
- Zombie (Z): Process finished but parent didn’t clean it
- Idle: Waiting, no CPU usage

## What systemd Does & Why It Matters

### What systemd Does

- Starts services at boot
- Stops and restarts services
- Handles service dependencies
- Maintains logs using journalctl

## Why systemd Matters

- Faster boot time
- Automatic recovery from failures
- Centralized logging
- Simplified service management

## Daily Linux Commands for DevOps

- ps aux → View running processes
- top → Live CPU and memory usage
- systemctl status <service> → Check service health
- journalctl -u <service> → View service logs
- df -h → Check disk space
