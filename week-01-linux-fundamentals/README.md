Home Lab — Linux & Cybersecurity Fundamentals

#Intro

## Week 1 Lab Documentation

**Environment:** Kali Linux running in UTM on an Apple Silicon (M1) Mac  
**Lab Type:** Isolated personal/home training environment  
**Focus:** Operating system fundamentals, Linux administration, networking, and cybersecurity foundations

---

## 1. Objective

The objective of this initial home-lab phase is to establish a practical foundation in Linux system administration, networking, permissions, processes, and basic security concepts.

The lab is being structured progressively so that foundational operating-system knowledge is established before introducing more advanced security tooling.

A secondary objective is to eventually incorporate a Windows environment to develop cross-platform administration skills and, later, Windows/Active Directory security knowledge.

---

# Day 1 — Linux Fundamentals

## 2. Lab Environment

A Kali Linux virtual machine was used as the primary training system.

The Windows 7 VM was also explored as a potential training platform; however, installation encountered UEFI/QEMU storage/boot issues. As a result, Kali Linux was selected as the primary platform for the initial training period.

Because the host system uses an Apple M1 processor, Windows 7 requires x86 emulation rather than ARM virtualization. Windows 7 will therefore be revisited after the Linux fundamentals portion of the lab.

---

## 3. Directory and File Management

A dedicated lab directory was created:

```text
~/home-lab/day1
```

The following directories were created:

```text
documents/
logs/
scripts/
```

File-management operations were practiced using:

```text
pwd
ls
ls -la
cd
mkdir
touch
cp
mv
rm
```

The exercises demonstrated:

- Determining the current working directory.
- Listing files and directories.
- Creating directories.
- Creating files.
- Navigating the filesystem.
- Copying files.
- Moving files.
- Removing files.

A basic text file was created and modified using `echo`, then reviewed using `cat` and `less`.

---

## 4. Linux Users and Groups

The Linux user/account structure was explored using:

```text
whoami
id
groups
```

These commands were used to identify:

- Current username.
- User ID (UID).
- Primary and supplementary groups.
- User/group relationships.

The `/etc/passwd` file was also examined:

```text
cat /etc/passwd
```

Filtering was demonstrated with:

```text
grep /bin/bash /etc/passwd
```

This introduced the concept of using command pipelines and filtering system information.

---

## 5. File Permissions

Linux filesystem permissions were investigated using:

```text
ls -l
chmod
```

The basic permission model was reviewed:

```text
-rw-r--r--
```

Permissions were considered in terms of:

- Owner
- Group
- Others
- Read
- Write
- Execute

A test file's permissions were modified using:

```text
chmod u-w notes.txt
```

and restored with:

```text
chmod u+w notes.txt
```

The more restrictive permission configuration was also practiced:

```text
chmod 600 notes.txt
```

This resulted in the owner retaining read/write access while group and other users were denied access.

The exercise established a foundation for understanding Linux access control and how filesystem permissions contribute to system security.

---

## 6. Processes

Running processes were investigated using:

```text
ps
ps aux
top
```

The following concept was introduced:

```text
ps aux | less
```

This demonstrated the use of the Linux pipe (`|`) to pass command output into another command.

Process filtering was also practiced:

```text
ps aux | grep bash
```

This established basic familiarity with:

- Running processes.
- Process ownership.
- System resource usage.
- Process filtering.

---

## 7. Networking Fundamentals

Network configuration was examined using:

```text
ip addr
ip route
```

The exercises focused on identifying:

- Network interfaces.
- IPv4 addresses.
- Network configuration.
- Default gateway.

Basic network connectivity was tested with:

```text
ping -c 4 8.8.8.8
```

DNS/name resolution was separately tested with:

```text
ping -c 4 google.com
```

This introduced an important troubleshooting distinction between basic IP connectivity and DNS/name-resolution problems.

---

## 8. Listening Network Services

Network sockets were examined using:

```text
ss -tuln
```

This introduced the concept of identifying services listening on TCP/UDP ports.

The long-term objective is to be able to determine:

- What ports are open.
- Which services are listening.
- Which interfaces are exposing those services.
- Whether a service should be accessible from the network.

---

## 9. File Searching

The `find` command was introduced:

```text
find . -type f
```

Specific file types were located with:

```text
find . -name "*.txt"
find . -name "*.log"
```

This established a practical method for locating files during system administration and troubleshooting.

---

## 10. System Information

Basic host information was collected using:

```text
uname -a
hostname
uptime
df -h
```

These commands provide information regarding:

- Operating system/kernel.
- Hostname.
- System uptime.
- Filesystem/storage utilization.

---

# Day 1 — Practical Outcome

By the end of Day 1, the following foundational Linux concepts had been introduced:

- Filesystem navigation.
- File and directory management.
- Linux users and groups.
- File permissions.
- Processes.
- Basic networking.
- Network routes.
- DNS testing.
- Listening ports.
- File searching.
- System information gathering.
- Command pipelines and filtering.

The exercises were designed to build operational familiarity with Linux rather than simply memorize commands.
