# Module 7: File Permissions & Ownership

## Understanding Permission Types
- **Read (r / 4):** View file contents or list directory
- **Write (w / 2):** Modify file or directory contents
- **Execute (x / 1):** Run file as a program or access directory

**Symbolic Representation:**
- r = read
- w = write
- x = execute

**Numeric Representation:**
- 4 = read
- 2 = write
- 1 = execute

**Examples:**
- rwx = 4+2+1 = 7 (full permissions)
- rw- = 4+2+0 = 6 (read and write)
- r-- = 4+0+0 = 4 (read only)

A typical permission string:
```bash
$ ls -l file.txt
-rwxr-xr-- 1 user group 0 Jan  4 10:00 file.txt
```
- The string `-rwxr-xr--` shows permissions for user (rwx = 7), group (r-x = 5), and others (r-- = 4).

## Changing Permissions: chmod
- `chmod` changes file/directory permissions
- Symbolic mode:
  - `chmod u+x file.txt` (add execute for user)
  - `chmod go-w file.txt` (remove write for group/others)
- Numeric mode:
  - `chmod 755 script.sh` (rwxr-xr-x)

Examples:
```bash
$ chmod 755 script.sh
$ ls -l script.sh
-rwxr-xr-x 1 user group 0 Jan  4 10:01 script.sh
```

## Changing Ownership: chown and chgrp
- `chown` changes file owner
  - `chown newuser file.txt`
- `chgrp` changes group ownership
  - `chgrp newgroup file.txt`

Examples:
```bash
$ chown alice file.txt
$ chgrp staff file.txt
$ ls -l file.txt
-rw-r--r-- 1 alice staff 0 Jan  4 10:02 file.txt
```

## User and Group Management Basics
- `/etc/passwd` - User account information
- `/etc/group` - Group information
- `id` - Show current user and group info
- `adduser` or `useradd` - Add new user
- `groupadd` - Add new group

Examples:
```bash
$ id
uid=1000(alice) gid=1000(staff) groups=1000(staff),27(sudo)
$ cat /etc/passwd | head -3
root:x:0:0:root:/root:/bin/bash
user:x:1000:1000:User,,,:/home/user:/bin/bash
alice:x:1001:1000:Alice,,,:/home/alice:/bin/bash
```

## Special Permissions
- **SUID (Set User ID):** File runs with owner's permissions
- **SGID (Set Group ID):** File runs with group's permissions; directories inherit group
- **Sticky Bit:** Only owner/root can delete files in directory

Examples:
```bash
$ chmod u+s file.sh   # Set SUID
$ chmod g+s dir/      # Set SGID
$ chmod +t /tmp       # Set sticky bit
$ ls -l file.sh dir /tmp
-rwsr-xr-x 1 user group 0 Jan  4 10:03 file.sh  # SUID (s)
drwxr-sr-x 2 user group 4096 Jan  4 10:03 dir   # SGID (s)
drwxrwxrwt 10 root root 4096 Jan  4 10:03 /tmp  # Sticky (t)
```
