
# Day 04 : Add Script Execution Permissions
In a bid to automate backup processes, the `xFusionCorp Industries` sysadmin team has developed a new bash script named `xfusioncorp.sh`. While the script has been distributed to all necessary servers, it lacks executable permissions on `App Server 1` within the Stratos Datacenter.


## Task :


## Solution :

### Step 1 : Check current file permissions
List the files in /tmp directory to list the current permissions of xfusioncorp.sh.
```
ls -l /tmp
```
### Step 2 : Add executable permissions to all users
Add executable permissions to all users (owner, group, others) for the script file.
```
sudo chmod a+x /tmp/xfusioncorp.sh
```
### Step 3 : Verify the updated permissions
Verify the updated permissions to confirm.
```
ls -l /tmp/xfusioncorp.sh
```
### Step 4 : Test script execution
Run the script to ensure it executes successfully.
```
bash /tmp/xfusioncorp.sh
```

## Additional Information

Make globally executable: Consider moving to `/usr/local/bin/` for system-wide access
