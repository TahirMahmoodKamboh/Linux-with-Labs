# Module 6: Users and Groups

## User Management
- **View current user:**
  ```bash
  $ whoami
  student
  $ id
  uid=1000(student) gid=1000(student) groups=1000(student),27(sudo)
  ```
- **List all users:**
  ```bash
  $ cat /etc/passwd | cut -d: -f1
  root
  student
  guest
  ```
- **Add a new user:**
  ```bash
  $ sudo adduser alice
  ```
- **Delete a user:**
  ```bash
  $ sudo deluser alice
  ```

## Group Management
- **List all groups:**
  ```bash
  $ cat /etc/group | cut -d: -f1
  root
  sudo
  staff
  student
  ```
- **Add a new group:**
  ```bash
  $ sudo addgroup editors
  ```
- **Add user to group:**
  ```bash
  $ sudo usermod -aG editors alice
  ```
- **Remove user from group:**
  ```bash
  $ sudo gpasswd -d alice editors
  ```

## Viewing User and Group Info
- **Show groups for a user:**
  ```bash
  $ groups alice
  alice : alice editors
  ```
- **Show group membership for current user:**
  ```bash
  $ groups
  student : student sudo
  ```

## User and Group Files
- `/etc/passwd` - User account information
- `/etc/group` - Group information
- `/etc/shadow` - Encrypted user passwords (root only)

## Best Practices
- Use strong passwords for all users
- Remove unused users and groups
- Limit sudo/root access to trusted users
- Regularly review user and group lists
