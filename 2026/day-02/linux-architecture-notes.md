Day 02 – Linux Architecture, Processes, and system 
__________________________________________________________________________________________
Task
__________________________________________________________________________________________
What is the Linux : 
Linux is a free and open-source operating system that manages a computer’s hardware resources and provides a platform for users and applications to run programs efficiently and securely. 
Linux Architecture:

        USER
         |
+----------------------+
|   Applications       |
| (Chrome, Python)     |
|   Shell (bash)       |
|   systemd (PID 1)    |
+----------------------+
           |
      system calls
           |
+----------------------+
|       KERNEL         |
| CPU | Memory | I/O   |
| File System          |
+----------------------+
           |
+----------------------+
|      HARDWARE        |
| CPU | RAM | Disk     |
+----------------------+
 
Core Components of Linux
1)The Linux Kernel (The Brain)
•	Controls CPU, memory, devices
•	Manages processes
•	Handles file system
•	Provides security & permissions
The kernel is the core of Linux that manages system resources and communicates with hardware.
Example Kernel = Head Chef
Controls kitchen (CPU, RAM, devices)
Decides which order to cook first
No one can touch kitchen without permission
If chef stops → shop closes (system crash)

2) User Space (Where We Live)
User space is the area where users and applications run and interact with the system.
Includes:
•	Applications (Chrome, Python, etc.)
•	Shell (bash)
•	System services (systemd)
Example : User Space = Customers & Waiters
Customers = You
Waiters = Shell (bash)
Orders = Applications (Chrome, Python)
Customers cannot cook directly.
They give order → waiter → chef.

3)Init System / systemd (The Startup Manager)
Systemd is the init system (First process (PID 1)) that starts and manages system services during boot.
Example : Ssystemd = Shop Manager
Opens shop in the morning
Starts staff (services)
Checks if staff is working
Closes shop properly
First person in shop (PID 1)

How Processes Work in Linux

What is a Process?
A process is a program that is currently running.
Example:
Double-click Chrome → Chrome becomes a process
Open Calculator → Calculator becomes another process

Process (Linux) – Key Points
•	A process is a running program
•	Each process has a PID (Process ID)
•	systemd is the first process (PID 1)
•	Process is created using fork
•	Program runs using exec
•	Kernel controls all processes
•	CPU time is shared between processes
•	Process can be running or waiting
•	Process uses memory
•	Process can be stopped using kill

Process Life Cycle (Linux)

1.	New = Process is created (fork)
2.	 Ready = Waiting for CPU
3.	 Running = Using CPU and working
4.	 Waiting / Sleeping = Waiting for input or file
5.	 Terminated = Work finished, process ends

How a Process is Created?
Step 1: fork() – Hiring a New Employee 
Parent process creates a child process
Child is a copy of parent
Example:
Shell (bash) → creates a child

Step 2: exec() – Assigning a Job 
Child process loads a new program
Now it becomes Chrome, Python, etc.

Explain process states (running, sleeping, zombie, etc.)

| State    | Meaning                  | Example                           |
| -------- | ------------------------ | --------------------------------- |
| Running  | Using CPU                | Employee working                  |
| Sleeping | Waiting                  | Waiting for file                  |
| Stopped  | Paused                   | Tea break                         |
| Zombie   | Finished but not cleaned | Left job, ID card not returned    |

systemd Deep Dive
Why systemd Matters for DevOps
PID 1 – systemd is the first process started at boot.
Unit – A resource managed by systemd (service, socket, timer, mount).
Service – A running program managed by systemd (.service unit).
Target – Group of units (like runlevels in old init).
Journal – Centralized logging (journalctl command).
Enable / Disable – Start services automatically on boot or not.
Start / Stop / Restart – Control services manually.
Dependency Management – systemd knows which services need others.
Mask / Unmask – Prevent or allow a service from running.
Timers – Schedule tasks (like cron jobs) using systemd timers.

Key systemd Concepts
systemd → manages services, logs, boot, dependencies, and timers.
Units → resources like service, socket, timer.
Targets → group of units (like runlevels).
Journal → centralized logs.
Enable/Disable, Mask/Unmask, Start/Stop/Restart → control services.



