
# Day 02 : Create Temporary User with Expiry Date

As part of the temporary assignment to the `Nautilus` project, a developer named `ravi` requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed.

## Task :
Create a user named `ravi` on `App Server 3` in Stratos Datacenter. Set the expiry date to `2026-12-07`, ensuring the user is created in lowercase as per standard protocol.

## Solution :

### Step 1 : Check if user 'ravi' already exists
```
cat /etc/passwd | grep ravi
```

### Step 2 : Create user 'ravi' with expiry date
```
sudo useradd -e 2026-12-07 ravi
```
### Step 3 : Verify user creation and expiry date
```
sudo chage -l ravi
```


## Additional Information

* Check User Details : `id ravi`
* Modify Expiry Date : `sudo chage -E 2026-12-07 ravi`
* Remove Expiry Date : `sudo chage -E -1 ravi`
* Delete the User : `sudo userdel ravi`
