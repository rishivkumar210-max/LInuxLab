# Experiment 8: Shell Programming

## 1. Process Control and Signals

Processes receive signals for control.

-   `kill -l` → list all signals\
-   **Common signals:**
    -   SIGINT (2) -- interrupt\
    -   SIGTERM (15) -- graceful stop\
    -   SIGKILL (9) -- force kill

Example:

    kill -9 1234

## 2. Process Monitoring and Resource Usage

Commands: - `top` -- live process view\
- `htop` -- improved top\
- `ps aux` -- all processes\
- `free -h` -- memory usage\
- `uptime` -- load averages

## 3. Process Communication

Processes communicate using pipes, files, sockets.

Example:

    ps aux | grep bash

## 4. Process Synchronization

Wait for background jobs:

``` bash
sleep 5 &
wait
echo "Finished after 5 seconds"
```

## 5. Background Processes and Job Control

    sleep 30 &
    jobs
    fg %1
    bg %1

## 6. System Monitoring and Logging

-   `dmesg | less`
-   `journalctl`
-   `last`
-   `who`, `w`

------------------------------------------------------------------------

# Lab Exercises

## i. Check File Permissions

``` bash
#!/bin/bash
echo "Enter filename:"
read file

if [ -e "$file" ]; then
    [ -r "$file" ] && echo "File is readable"
    [ -w "$file" ] && echo "File is writable"
    [ -x "$file" ] && echo "File is executable"
else
    echo "File does not exist."
fi
```

## ii. String Operations

``` bash
#!/bin/bash
echo "Enter first string:"
read str1
echo "Enter second string:"
read str2

echo "Length of first string: ${#str1}"
echo "Length of second string: ${#str2}"

concat="$str1$str2"
echo "Concatenated string: $concat"

if [ "$str1" = "$str2" ]; then
    echo "Strings are equal"
else
    echo "Strings are not equal"
fi
```

## iii. Search for a Pattern in a File

``` bash
#!/bin/bash
echo "Enter filename:"
read file
echo "Enter pattern to search:"
read pattern

if [ -e "$file" ]; then
    echo "Matching lines:"
    grep "$pattern" "$file"
else
    echo "File not found!"
fi
```

## iv. Display System Information

``` bash
#!/bin/bash
echo "System Information:"
echo "-------------------"
echo "Date and Time: $(date)"
echo "Logged in users: $(who)"
echo "System Uptime: $(uptime -p)"
echo "Memory Usage:"
free -h
echo "Disk Usage:"
df -h
```

------------------------------------------------------------------------

# Assignment

1.  Script to start background job, list jobs, bring to foreground,
    terminate.\

2.  Compare two files using `cmp` or `diff`.\

3.  Count user processes:

        ps -u $USER | wc -l

4.  Monitor memory usage every 5 seconds using `free -m` + loop.\

5.  Prompt for filename + pattern and count matches using `grep -c`.
