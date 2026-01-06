# Username & Password Validation

```
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
