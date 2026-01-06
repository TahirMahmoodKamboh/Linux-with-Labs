**Lab 1**

* Takes **username and password as user input**
* Compares them with **predefined variables**
* Prints whether **login is successful or failed**
* Uses **secure password input** (password not shown on screen)

---

## Bash Script: Username & Password Validation

```bash
#!/bin/bash

# Predefined credentials
VALID_USERNAME="admin"
VALID_PASSWORD="secret123"

# Take username input
read -p "Enter username: " USERNAME

# Take password input (silent)
read -s -p "Enter password: " PASSWORD
echo

# Compare credentials
if [[ "$USERNAME" == "$VALID_USERNAME" && "$PASSWORD" == "$VALID_PASSWORD" ]]; then
    echo "Login successful"
else
    echo "Login failed: Invalid username or password"
fi
```

---

## How to Run the Script

```bash
chmod +x login.sh
./login.sh
```

---

## Output Example

**Successful login**

```text
Enter username: admin
Enter password:
Login successful
```

**Failed login**

```text
Enter username: user1
Enter password:
Login failed: Invalid username or password
```

---

## Key Concepts (Exam-Oriented Notes – RHCSA / LPIC)

| Concept   | Explanation                               |
| --------- | ----------------------------------------- |
| `read -p` | Takes input with prompt                   |
| `read -s` | Takes input silently (used for passwords) |
| `[[ ]]`   | Preferred test syntax in Bash             |
| `&&`      | Logical AND                               |
| `==`      | String comparison                         |
| Variables | No spaces around `=` in Bash              |

---

## Common Mistakes (Very Important for Exams)

❌ Using spaces in variable assignment

```bash
USER = "admin"   # WRONG
```

✅ Correct

```bash
USER="admin"
```

❌ Using `=` instead of `==` in condition

```bash
if [ "$A" = "$B" ]   # acceptable
if [[ "$A" == "$B" ]] # preferred
```

---
Below is a **single, RHCSA-aligned Bash authentication script** that implements **all requested features** using only **core Linux utilities** typically available on RHEL / Rocky / Alma / CentOS systems.

No advanced libraries, no external dependencies beyond standard tools (`sha256sum`, `cut`, `grep`, `read`).

---

# RHCSA-Style Bash Login Script (Complete)

### Features Implemented

* Login attempt limit (**3 tries**)
* **Password hashing** (SHA-256)
* **File-based authentication**
* **case-based login logic**
* POSIX-safe Bash practices (RHCSA compliant)

---

## 1. User Database File (Plain Text)

Create a file called `users.db`

```bash
admin:ef92b778bafe771e89245b89ecbc08a44a4e166c06659911881f383d4473e94f
user1:5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8
```

**Format**

```
username:hashed_password
```

---

## 2. How to Generate Password Hash (Admin Task)

```bash
echo -n "secret123" | sha256sum | cut -d' ' -f1
```

(Use this command to add new users)

---

## 3. Login Script (RHCSA-Aligned)

Save as `login.sh`

```bash
#!/bin/bash

USER_DB="./users.db"
MAX_ATTEMPTS=3
ATTEMPT=1

# Check if user database exists
if [[ ! -f "$USER_DB" ]]; then
    echo "Authentication database not found"
    exit 1
fi

while [[ $ATTEMPT -le $MAX_ATTEMPTS ]]; do

    read -p "Username: " USERNAME
    read -s -p "Password: " PASSWORD
    echo

    # Hash entered password
    HASHED_PASS=$(echo -n "$PASSWORD" | sha256sum | cut -d' ' -f1)

    # Fetch user record
    RECORD=$(grep "^${USERNAME}:" "$USER_DB")

    case "$RECORD" in
        "")
            echo "User does not exist"
            ;;
        *)
            STORED_HASH=$(echo "$RECORD" | cut -d':' -f2)

            case "$HASHED_PASS" in
                "$STORED_HASH")
                    echo "Login successful"
                    exit 0
                    ;;
                *)
                    echo "Invalid password"
                    ;;
            esac
            ;;
    esac

    ATTEMPT=$((ATTEMPT + 1))
    echo "Attempts left: $((MAX_ATTEMPTS - ATTEMPT + 1))"
    echo

done

echo "Account locked. Maximum login attempts exceeded."
exit 1
```

---

## 4. Permissions (RHCSA Best Practice)

```bash
chmod 700 login.sh
chmod 600 users.db
```

---

## 5. Execution

```bash
./login.sh
```

---

## 6. Output Example

### Successful Login

```
Username: admin
Password:
Login successful
```

### Failed Login (3 Attempts)

```
Invalid password
Attempts left: 2

Invalid password
Attempts left: 1

Account locked. Maximum login attempts exceeded.
```

---

## 7. RHCSA / LPIC Exam-Focused Concepts Used

| Concept                 | Why It Matters                    |
| ----------------------- | --------------------------------- |
| `read -s`               | Secure password entry             |
| `sha256sum`             | Standard hashing utility          |
| `cut`, `grep`           | Text processing (core exam skill) |
| `case`                  | Required shell control structure  |
| File permissions        | Security objective                |
| Exit codes              | Script correctness                |
| No arrays / no bashisms | POSIX safety                      |

---

## 8. Why This Script Is RHCSA-Aligned

* No PAM modification (not allowed in RHCSA)
* No `/etc/shadow` manipulation
* No external scripting languages
* No advanced crypto libraries
* Uses **only standard shell + coreutils**

---
