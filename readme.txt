
sshlog is a one line patch to OpenSSH portable that logs user names and passwords.
The patch is intended for cyber security research, honeypots, etc. 

To apply the patch

Download OpenSSH Portable source code (http://www.openssh.com/portable.html).
Then apply the patch and build OpenSSH per the normal process.

Example sshlog entries in /var/log/auth.log

    sshlog: root hamlet
    sshlog: root password123
    sshlog: root king!!!

To avoid logging legitimate user passwords, use ssh keys.

