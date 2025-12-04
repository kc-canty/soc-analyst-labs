Lab 01 – Linux CLI Fundamentals & Log Peeking (BEGINNER)
Basic navigation, file operations, viewing logs, and documenting findings.

# Lab 01 – Linux CLI Fundamentals & Log Peeking

## Overview

This beginner-level lab demonstrates my ability to work in the Linux command line:
- Navigate the filesystem
- Create and manage directories and files
- Use basic text-viewing commands (e.g., `cat`, `less`, `tail`)
- Use simple search and filtering with `grep`
- Document findings in a structured, repeatable way

This lab is designed to be the first step in my Linux projects portfolio, building toward more advanced system administration and security-focused labs.

---

## Scenario

You are a junior technician who has just SSH’d into a Linux server.  
Your lead asks you to:

1. Confirm where you are in the filesystem.
2. Explore your home directory and organize a small “lab workspace”.
3. View a system log file and confirm it’s actively recording events.
4. Search the log file for failed login attempts.
5. Capture your commands and findings for future reference.

---

## Environment

- **OS**: Any Linux distribution (Ubuntu/Debian recommended)
- **Access**: Local VM or remote server with terminal/SSH access
- **Account**: Non-root user with read access to `/var/log` (typical on most systems)

---

## Learning Objectives

By the end of this lab I will be able to:

1. Use basic navigation commands: `pwd`, `ls`, `cd`
2. Create and manage files/directories: `mkdir`, `touch`, `rm`, `rmdir`
3. Read and search log files: `cat`, `less`, `tail`, `grep`
4. Use redirection and pipes: `>` and `|`
5. Summarize what I did in a clear, portfolio-ready format

---

## Lab Tasks

### Task 1 – Confirm Your Location and List Files

1. Open a terminal or SSH into Linux machine.
2. Run the following command to show current location:

   ```bash
   pwd
