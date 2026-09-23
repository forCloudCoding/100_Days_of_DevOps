
# Day 03 : Secure Root SSH Access
Following security audits, the `xFusionCorp Industries` security team has rolled out new protocols, including the restriction of direct root SSH login.


## Task :
Disable direct SSH root login on all app servers within the `Stratos Datacenter`.

## Solution :

### Step 1 : Login to each app server
Access each application server in the Stratos Datacenter to apply the SSH configuration changes. i.e., `app01, app02, app03`

```
# Login Commands for each server
ssh user@app01
ssh user@app02  
ssh user@app03
```

### Step 2 : Open SSH daemon configuration file

Open the SSH daemon configuration file for editing. Find the line containing PermitRootLogin and modify its value from `yes` to `no`.  This setting disables direct root login via SSH, thereby improving system security.

```
sudo vi /etc/ssh/sshd_config
```

### Step 3 : Restart SSH service to apply changes

Restart the SSH service to apply configuration changes.

```
sudo systemctl restart sshd
```

### Step 4 : Verify the configuration change
Verify that root login is disabled by checking the configuration.
```
sudo cat /etc/ssh/sshd_config | grep -i "permitrootlogin"
```
## Additional Information

Before making changes: sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.backup

