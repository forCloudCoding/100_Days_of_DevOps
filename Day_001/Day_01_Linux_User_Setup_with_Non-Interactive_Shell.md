
# Day 01 : Linux User Setup with Non-Interactive Shell

To accommodate the backup agent tool's specifications, the system admin team at `xFusionCorp Industries` requires the creation of a user with a non-interactive shell. Here's your task:

## Task :
Create a user named `rose` with a non-interactive shell on `App Server 1`.

## Solution :

### Step 1 : Switch to Root User for Administrative Privileges
```
sudo su -
```
Using this command we can switch to the root user with full administrative privileges.

### Step 2 : Verify if any other user already exists with the same name 'rose'
```
cat /etc/passwd | grep rose
```

### Step 3 : Create a new user 'rose' with a non-interactive shell

```
sudo useradd rose --shell /sbin/nologin
```
Note: Non-interactive shells are needed for Service Accounts. [ i.e., System to System logins ]

### Step 4 : Verify the user Creation

Check the User ID and Groups.
```
id rose
```
Check the user entry in `passwd` file.
```
getent passwd rose
```

## Additional Information

* Delete the User : `sudo userdel rose`
* Delete User and Home Directory : `sudo userdel -r rose`
* Change User Shell later : `sudo usermod -s /bin/bash rose`
