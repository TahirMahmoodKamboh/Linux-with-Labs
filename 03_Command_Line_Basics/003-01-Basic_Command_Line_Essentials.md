# **Streamlined Module 3: Basic Command Line Essentials**

## **Module 3: Essential First Commands**

### **3.1 User Identity & System Info**
- `whoami` - "Who am I?" - Shows your username
- `id` - Shows detailed user and group information
  - Try: `id`, `id -u`, `id -g`
- `who` - Shows who else is logged in
- `w` - Shows who's logged in and what they're doing

### **3.2 System Basics**
- `uname` - System information
  - `uname -a` - Shows all system details
- `hostname` - Your computer's name
- `date` - Current date and time
  - `date +"%H:%M"` - Just show time
- `cal` - Calendar
  - `cal` - This month
  - `cal 2024` - Whole year

### **3.3 Getting Help**
- `man` - Manual (help) pages
  - `man ls` - Read about ls command
  - Press `q` to quit
- `--help` - Quick help
  - `ls --help` - Short help for ls
- `whatis` - One-line description
  - `whatis ls` - Brief description

### **3.4 Basic Navigation**
- `pwd` - "Print Working Directory" - Where am I?
- `ls` - List files and folders
  - `ls` - Simple list
  - `ls -l` - Detailed list
  - `ls -a` - Show hidden files too
- `cd` - Change Directory
  - `cd` - Go home
  - `cd ..` - Go up one level
  - `cd folder_name` - Enter folder
  - `cd /` - Go to root

### **3.5 Simple File Operations**
- `touch` - Create empty file
  - `touch notes.txt` - Creates notes.txt
- `mkdir` - Make Directory (folder)
  - `mkdir projects` - Creates projects folder
- `cat` - View file contents
  - `cat notes.txt` - Shows what's in notes.txt

### **3.6 Terminal Tips**
- `clear` - Clean your screen (or Ctrl+L)
- `exit` - Close terminal (or Ctrl+D)
- `Ctrl+C` - Stop/cancel current command
- **Tab key** - Auto-complete commands
- **Up/Down arrows** - Previous commands

---

## **Practice Session (5 Minutes)**

### **Try these commands in order:**

```bash
# 1. Check who you are
whoami

# 2. See your user details
id

# 3. Check what system you're on
uname -a

# 4. See where you are
pwd

# 5. Look around
ls
ls -l

# 6. Create a practice folder
mkdir mypractice

# 7. Go into it
cd mypractice

# 8. Create a file
touch hello.txt

# 9. Check it's there
ls

# 10. Go back home
cd

# 11. Check help for any command
man ls
# (press q to quit)
```

---

## **Quick Reference Card**

| Command | What it does | Example |
|---------|--------------|---------|
| `whoami` | Shows your username | `whoami` |
| `id` | Shows user/group info | `id` |
| `pwd` | Shows current location | `pwd` |
| `ls` | Lists files/folders | `ls -l` |
| `cd` | Changes directory | `cd ..` |
| `mkdir` | Creates folder | `mkdir docs` |
| `touch` | Creates file | `touch file.txt` |
| `cat` | Shows file content | `cat file.txt` |
| `date` | Shows date/time | `date` |
| `clear` | Clears screen | `clear` |

### **Bash Examples with Output**

```bash
$ whoami
student

$ id
uid=1000(student) gid=1000(student) groups=1000(student),27(sudo)

$ pwd
/home/student

$ ls -l
total 4
-rw-r--r-- 1 student student    0 Jan  4 10:00 file.txt
drwxr-xr-x 2 student student 4096 Jan  4 09:59 docs

$ cd ..
$ pwd
/home

$ mkdir docs
$ touch file.txt
$ cat file.txt
# (no output, file is empty)

$ date
Sat Jan  4 10:05:00 UTC 2026

$ clear
# (screen is cleared)
```

---

## **Learning Goals**
By the end of this module, you'll be able to:
1. Identify yourself on the system ✅
2. Navigate basic folders ✅  
3. Create simple files and folders ✅
4. Get system information ✅
5. Use help when needed ✅
6. Clean up your terminal ✅

That's it! These are the absolute essential commands to get started. Once comfortable with these, you'll be ready for more advanced operations.
