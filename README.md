# Privilege Scalation
## Linux
* Environment variables:  
```env```  
* Print all usernames and password hashes:  
`cat /etc/shadow`  
* Command history:  
`history`
* Kernel version and architecture:  
`uname -a`  
* List sudoable commands [GTFOBins](https://gtfobins.github.io/):  
`sudo -l`  
* Path hijacking:  
`echo $PATH`

* SUID:  
`find / -perm -u=s -type f 2>/dev/null`  
If the executable is editable, edit and spawn a root shell.  
Otherwise, check which command executes the binary and perform PATH hijacking.  
Create an executable with the same name as the one that runs the binary with SUID enabled.  
Then, add the path where the new executable is (the one spawning a shell) to the PATH.  
Important to add it to the first position of the PATH.  
`export PATH='out binary location':$PATH`  
Execute the SUID program.
* Check cronjobs:  
`cat /etc/crontab`  
If we can edit it we can spawn a reverse shell with root privileges.
* Open shell sessions:  
`screen`  
`tmux`

* Tools:  
`linpeass.sh`