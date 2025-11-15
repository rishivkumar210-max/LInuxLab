# Linux File Manipulation and System Management Tutorial

## Slide 1: Linux File Manipulation and System Management Tutorial

## Slide 2: Lab Section I: Working with Files

## Slide 3: The `cp` Command (Recap)

## Slide 4: The `mv` Command (Recap)

## Slide 5: The `rm` Command

## Slide 6: Viewing File Contents

## Slide 7: The `less` Command

## Slide 8: The `head` Command

## Slide 9: Lab Section II: File Permissions and Ownership

## Slide 10: The `chmod` Command

## Slide 11: The `chown` Command

## Slide 12: Lab Section III: Advanced File and Directory Operations

## Slide 13: Pattern Searching with `grep`

## Slide 14: File Archiving with `tar`

## Slide 15: Creating Links with `ln`

---

# Linux File Manipulation and System Management Tutorial

## Theory Overview
### File Manipulation Commands
Linux provides powerful commands for creating, copying, moving, and removing files and directories.

### File Compression and Archiving
Compression reduces file size. Archiving bundles files for easy transfer.

### File Searching
Linux offers robust tools to locate files by name, content, or attributes.

### File System Navigation and Management
Understanding directory structures is essential for effective file management.

### File Transfer
Moving files between locations requires proper command usage and permissions.

---

# Lab Section I: Working with Files

## Creating and Managing Files
### The `touch` Command
```
touch newfile.txt
touch file1.txt file2.txt file3.txt
touch -t 202401151430 dated_file.txt
```
Options:
- `-t`
- `-a`
- `-m`

## The `cp` Command (Recap)
```
cp document.txt backup_document.txt
cp -r /home/user/documents /backup/
cp -i source.txt destination.txt
```

## The `mv` Command (Recap)
```
mv oldname.txt newname.txt
mv document.txt /home/user/documents/
```

## The `rm` Command
```
rm file.txt
rm -r folder/
rm -f stubborn.txt
```

---

# Viewing File Contents

## The `cat` Command
```
cat filename.txt
cat -n filename.txt
```

## The `less` Command
```
less filename.txt
```

## The `head` Command
```
head -n 5 filename.txt
```

## The `tail` Command
```
tail -n 20 filename.txt
```

---

# Lab Section II: Permissions and Ownership

## Understanding Permissions
```
-rw-r--r-- user group document.txt
```

## The `chmod` Command
```
chmod 755 script.sh
chmod u+x script.sh
```

## The `chown` Command
```
sudo chown newuser file.txt
```

## The `chgrp` Command
```
chgrp newgroup file.txt
```

---

# Lab Section III: Advanced File and Directory Operations

## File Searching with `find`
```
find /home -name "*.txt"
```

## Pattern Searching with `grep`
```
grep "error" logfile.txt
```

## Archiving with `tar`
```
tar -czf backup.tar.gz /home/user/documents
```

## Compression with `gzip`
```
gzip file.txt
```

## Creating Links with `ln`
```
ln original.txt hardlink.txt
ln -s /path/to/original symlink.txt
```
