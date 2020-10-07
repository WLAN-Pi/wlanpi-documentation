Title: Change the Password of the wlanpi User
Authors: Nigel Bowden

# Changing the password for the wlanpi user

Changing the default password for the wlanpi user is highly recommended to help secure your unit.

To change from the default password (which is 'wlanpi'), SSH to the WLANP Pi and use the 'passwd' command as follows:

```
wlanpi@wlanpi:~$ passwd
Changing password for wlanpi.
(current) UNIX password: wlanpi
Enter new UNIX password: <enter new pwd>
Retype new UNIX password: <enter new pwd again>
passwd: password updated successfully
wlanpi@wlanpi:~$
```

**If connecting the WLAN Pi to any network, changing the default password should be a top priority. If the WLAN Pi becomes compromised as default credentials have been left in place, this could have very serious consequences.**


[<-- back][back]

<!-- Link list -->
[back]: index.md
