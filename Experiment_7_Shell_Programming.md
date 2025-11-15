# Experiment 7: Shell Programming

## 1. Processes

A process is an instance of a running program.

-   Each process has a unique PID (Process ID)
-   Parent process has PPID

### Command: `ps`

Shows running processes.

Example:

      PID TTY          TIME CMD
     1234 pts/0    00:00:00 bash
     1256 pts/0    00:00:00 ps

## 2. Process States

-   **Running (R)**
-   **Sleeping (S)**
-   **Stopped (T)**
-   **Zombie (Z)**

### Command: `top`

Displays dynamic list of processes.

## 3. Process Hierarchy

### Command: `pstree`

Shows parent-child relationship.

Example:

    systemd─┬─bash───pstree

## 4. Killing Processes

    kill <PID>
    kill -9 <PID>

## 5. Process Prioritization

Lower nice value = higher priority.

    nice -n <value> command
    renice <value> -p <PID>

## 6. Scheduling Processes

### One‑time tasks: `at`

    echo "ls > output.txt" | at now + 1 minute

### Repeating tasks: `cron`

    crontab -e
    * * * * * date >> time.log

## Lab Exercises

### i. Check if File Exists

``` bash
#!/bin/bash
echo "Enter filename: "
read file

if [ -e "$file" ]
then
    echo "File exists. Contents are:"
    cat "$file"
else
    echo "File does not exist."
    echo "Do you want to create it? (y/n)"
    read choice
    if [ "$choice" = "y" ]; then
        touch "$file"
        echo "File $file created."
    fi
fi
```

### ii. Print Numbers 1‑10

``` bash
for i in {1..10}
do
    echo $i
done
```

### iii. Count Lines, Words, Characters

``` bash
#!/bin/bash
if [ $# -eq 0 ]
then
    echo "Usage: $0 filename"
    exit 1
fi

file=$1

if [ -e "$file" ]
then
    echo "Lines: $(wc -l < $file)"
    echo "Words: $(wc -w < $file)"
    echo "Characters: $(wc -m < $file)"
else
    echo "File not found!"
fi
```

### iv. Factorial Function

``` bash
factorial() {
    num=$1
    fact=1
    while [ $num -gt 1 ]
    do
        fact=$((fact * num))
        num=$((num - 1))
    done
    echo $fact
}

echo "Factorial of 5 is: $(factorial 5)"
```

## Assignment Tasks

1.  Monitor top 5 CPU-consuming processes every 10 seconds.\
    Hint:\
    `ps -eo pid,comm,%cpu --sort=-%cpu | head -6`

2.  Script to display details of a PID.\
    Hint:\
    `ps -p <PID> -o pid,ppid,state,comm,%mem`

3.  Cron task to log date/time every minute.

4.  Modify factorial to check for negative number.

5.  Script to count lines starting with vowels.\
    Hint:\
    `grep -i "^[aeiou]" filename | wc -l`

## Reference

-   crontab
