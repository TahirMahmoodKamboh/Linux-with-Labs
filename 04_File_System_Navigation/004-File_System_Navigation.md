# Module 4: File System Navigation 📁

## 4.1 Understanding Linux File Structure
- **Root directory (/):** Top-level directory in Linux
  ```bash
  $ ls /
  bin  boot  dev  etc  home  lib  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
  ```
- **Common directories and their purposes:**
  - `/home` - User directories
    ```bash
    $ ls /home
    student  guest
    ```
  - `/etc` - Configuration files
    ```bash
    $ ls /etc | head -5
    adduser.conf
    aliases
    alternatives
    apache2
    apt
    ```
  - `/var` - Variable data
    ```bash
    $ ls /var
    backups  cache  lib  local  lock  log  mail  opt  run  spool  tmp
    ```
  - `/tmp` - Temporary files
    ```bash
    $ ls /tmp
    tmpfile1  tmpfile2
    ```
  - `/bin`, `/sbin` - System binaries
    ```bash
    $ ls /bin | head -5
    bash
    cat
    chmod
    cp
    dash
    ```
    ```bash
    $ ls /sbin | head -5
    agetty
    badblocks
    blkid
    blockdev
    bridge
    ```
  - `/usr` - User programs and data
    ```bash
    $ ls /usr | head -5
    bin
    games
    include
    lib
    local
    ```

## 4.2 Advanced Navigation Commands
- **Absolute vs Relative Paths:**
  - `/home/user/documents` (absolute)
    ```bash
    $ cd /home/student/documents
    $ pwd
    /home/student/documents
    ```
  - `./documents` or `documents` (relative)
    ```bash
    $ cd documents
    $ pwd
    /home/student/documents
    ```
  - `../parent` (go up one level)
    ```bash
    $ cd ..
    $ pwd
    /home/student
    ```
- **Special Directory References:**
  - `.` - Current directory
    ```bash
    $ cd .
    $ pwd
    /home/student
    ```
  - `..` - Parent directory
    ```bash
    $ cd ..
    $ pwd
    /home
    ```
  - `~` - Home directory
    ```bash
    $ cd ~
    $ pwd
    /home/student
    ```
  - `-` - Previous directory
    ```bash
    $ cd -
    /etc
    $ pwd
    /etc
    ```

## 4.3 Navigation Practice
```bash
# Navigating with special characters
cd ~           # Go to home directory
cd ~/Documents # Go to Documents in home
cd /etc        # Go to etc from root
cd ..          # Go up one level
cd ../..       # Go up two levels
cd -           # Go back to previous directory
```

## 4.4 Listing Files with Options
- `ls -lh` - Human readable sizes + details
  ```bash
  $ ls -lh
  -rw-r--r-- 1 student student 1.1K Jan  4 10:00 file.txt
  drwxr-xr-x 2 student student 4.0K Jan  4 09:59 docs
  ```
- `ls -la` - All files including hidden
  ```bash
  $ ls -la
  drwxr-xr-x 2 student student 4096 Jan  4 09:59 .
  drwxr-xr-x 3 student student 4096 Jan  4 09:58 ..
  -rw-r--r-- 1 student student    0 Jan  4 10:00 .hiddenfile
  -rw-r--r-- 1 student student 1.1K Jan  4 10:00 file.txt
  ```
- `ls -lt` - Sorted by modification time
  ```bash
  $ ls -lt
  -rw-r--r-- 1 student student 1.1K Jan  4 10:00 file.txt
  drwxr-xr-x 2 student student 4.0K Jan  4 09:59 docs
  ```
- `ls -lS` - Sorted by size (largest first)
  ```bash
  $ ls -lS
  -rw-r--r-- 1 student student 1.1K Jan  4 10:00 file.txt
  drwxr-xr-x 2 student student 4.0K Jan  4 09:59 docs
  ```
- `ls -R` - Recursive listing
  ```bash
  $ ls -R
  .:
  docs  file.txt
  ./docs:
  notes.txt
  ```
- `ls -d */` - List only directories
  ```bash
  $ ls -d */
  docs/
  downloads/
  ```

## 4.5 Finding Your Way Around
- `tree` - Display directory structure
  ```bash
  $ tree
  .
  ├── docs
  │   └── notes.txt
  └── file.txt
  ```
- `tree -L 2` - Show 2 levels deep
  ```bash
  $ tree -L 2
  .
  ├── docs
  │   └── notes.txt
  └── file.txt
  ```
- `tree -d` - Show directories only
  ```bash
  $ tree -d
  .
  └── docs
  ```
- `realpath` - Show absolute path of a file
  ```bash
  $ realpath file.txt
  /home/student/file.txt
  ```
- `basename` - Get filename from path
  ```bash
  $ basename /home/student/file.txt
  file.txt
  ```
- `dirname` - Get directory from path
  ```bash
  $ dirname /home/student/file.txt
  /home/student
  ```

## 4.6 Navigation Exercises
- Explore system directories (read-only)
- Create a directory structure and navigate it
- Practice with absolute and relative paths
- Use different ls options to view files
