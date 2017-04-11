# sshlog

sshlog is a small patch for OpenSSH portable that logs user names, passwords
and IPs all on one line for easy parsing. The patch is intended for cyber
security research, honeypots, etc. 

## To apply the patch

Download the OpenSSH Portable source code (http://www.openssh.com/portable.html).
Then copy the patch into the OpenSSH folder and apply it. Finally, build
OpenSSH per the normal process.

```bash
$ patch --dry-run < sshlog.path
$ patch < sshlog.patch
$ ./configure
$ make
$ sudo make install
```

## Example sshlog entries in /var/log/auth.log

```bash
sshlog: root hamlet 1.2.3.4
sshlog: root password123 5.6.7.8
sshlog: root king!!! 1:2:3:4:5:6:7:8
```

## Notes

    * To avoid logging legitimate user connections, use ssh keys.

