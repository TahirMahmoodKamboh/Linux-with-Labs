# Module 5: File Operations & Management 📄

## 5.1 Creating Files & Directories
### Directories:
- `mkdir folder` - Create single directory
  ```bash
  $ mkdir folder
  $ ls
  folder
  ```
- `mkdir -p a/b/c` - Create nested directories
  ```bash
  $ mkdir -p a/b/c
  $ tree a
  a
  └── b
      └── c
  ```
- `mkdir dir1 dir2 dir3` - Create multiple directories
  ```bash
  $ mkdir dir1 dir2 dir3
  $ ls
  dir1  dir2  dir3
  ```
### Files:
- `touch file.txt` - Create empty file
  ```bash
  $ touch file.txt
  $ ls
  file.txt
  ```
- `touch file{1..5}.txt` - Create multiple files
  ```bash
  $ touch file{1..5}.txt
  $ ls
  file1.txt  file2.txt  file3.txt  file4.txt  file5.txt
  ```
- `touch -t 202401011200 file.txt` - Set specific timestamp
  ```bash
  $ touch -t 202401011200 file.txt
  $ ls -l file.txt
  -rw-r--r-- 1 user user 0 Jan  1 12:00 file.txt
  ```

## 5.2 Copying Files & Directories
- `cp source destination` - Copy file
  ```bash
  $ cp file.txt copy.txt
  $ ls
  copy.txt  file.txt
  ```
- `cp -r folder/ newfolder/` - Copy directory recursively
  ```bash
  $ cp -r folder/ newfolder/
  $ ls
  folder  newfolder
  ```
- `cp -i file.txt backup/` - Interactive (ask before overwrite)
  ```bash
  $ cp -i file.txt backup/
  cp: overwrite 'backup/file.txt'? y
  ```
- `cp -u source dest` - Update (copy only if newer)
  ```bash
  $ cp -u file.txt backup/
  ```
- `cp -v file.txt dest/` - Verbose (show what's happening)
  ```bash
  $ cp -v file.txt dest/
  'file.txt' -> 'dest/file.txt'
  ```
- `cp file1 file2 file3 destination/` - Copy multiple files
  ```bash
  $ cp file1.txt file2.txt file3.txt backup/
  ```

## 5.3 Moving & Renaming
- `mv source destination` - Move or rename
  ```bash
  $ mv file.txt folder/
  $ mv oldname.txt newname.txt
  ```
- `mv oldname.txt newname.txt` - Rename file
  ```bash
  $ mv oldname.txt newname.txt
  $ ls
  newname.txt
  ```
- `mv file.txt /new/location/` - Move file
  ```bash
  $ mv file.txt /new/location/
  ```
- `mv -i file.txt dest/` - Interactive move
  ```bash
  $ mv -i file.txt dest/
  mv: overwrite 'dest/file.txt'? y
  ```
- `mv -v folder/ newlocation/` - Verbose move
  ```bash
  $ mv -v folder/ newlocation/
  'folder/' -> 'newlocation/folder/'
  ```

## 5.4 Removing Files & Directories
- `rm file.txt` - Remove file
  ```bash
  $ rm file.txt
  ```
- `rm -i file.txt` - Interactive removal (ask)
  ```bash
  $ rm -i file.txt
  rm: remove regular empty file 'file.txt'? y
  ```
- `rm -f file.txt` - Force removal (no questions)
  ```bash
  $ rm -f file.txt
  ```
- `rm -r folder/` - Remove directory recursively
  ```bash
  $ rm -r folder/
  ```
- `rm -rf folder/` - Force remove directory
  ```bash
  $ rm -rf folder/
  ```
- `rmdir emptyfolder/` - Remove empty directory only
  ```bash
  $ rmdir emptyfolder/
  ```

## 5.5 Viewing File Contents
- `cat file.txt` - Display entire file
  ```bash
  $ cat file.txt
  Hello, world!
  ```
- `less file.txt` - Page through file
  ```bash
  $ less file.txt
  # (Use Space to scroll, q to quit)
  ```
- `more file.txt` - Similar to less (older)
  ```bash
  $ more file.txt
  # (Use Space to scroll, q to quit)
  ```
- `head -n 10 file.txt` - First 10 lines
  ```bash
  $ head -n 10 file.txt
  Line 1
  Line 2
  ...
  Line 10
  ```
- `tail -n 10 file.txt` - Last 10 lines
  ```bash
  $ tail -n 10 file.txt
  ...
  ```
- `tail -f logfile.log` - Follow file in real-time
  ```bash
  $ tail -f logfile.log
  # (Shows new lines as they are added)
  ```

## 5.6 File Information & Comparison
- `file filename` - Determine file type
  ```bash
  $ file file.txt
  file.txt: ASCII text
  ```
- `stat file.txt` - Detailed file statistics
  ```bash
  $ stat file.txt
  File: file.txt
  Size: 12         Blocks: 8          IO Block: 4096   regular file
  ...
  ```
- `wc file.txt` - Word count (lines, words, characters)
  ```bash
  $ wc file.txt
  1  2  12 file.txt
  ```
- `wc -l` - Line count only
  ```bash
  $ wc -l file.txt
  1 file.txt
  ```
- `wc -w` - Word count only
  ```bash
  $ wc -w file.txt
  2 file.txt
  ```
- `diff file1.txt file2.txt` - Compare files
  ```bash
  $ diff file1.txt file2.txt
  1c1
  < Hello
  ---
  > Hi
  ```
- `cmp file1.txt file2.txt` - Byte-by-byte comparison
  ```bash
  $ cmp file1.txt file2.txt
  file1.txt file2.txt differ: byte 1, line 1
  ```

## 5.7 File Operations Exercises
```bash
# Exercise 1: Create and organize
mkdir -p project/{docs,src,backup}
touch project/docs/{readme.txt,notes.txt}
cp project/docs/readme.txt project/backup/
mv project/docs/notes.txt project/docs/important_notes.txt

# Exercise 2: Cleanup practice
rm -i project/docs/readme.txt
rmdir project/backup/  # Will fail if not empty
rm -r project/backup/  # Remove with contents
```

## 5.8 Safety Tips & Best Practices
- Always use `-i` flag when learning
- Double-check paths before using `rm -rf`
- Keep backups of important files
- Use tab completion to avoid typos
- Test commands with echo first:
  ```bash
  $ echo rm -r folder/
  rm -r folder/
  ```
