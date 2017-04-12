# sshlog

sshlog is a small patch for OpenSSH portable that logs user name, password,
IP and epoch all on one line for easy parsing. The patch is intended for cyber
security research, honeypots, etc. 

## To apply the patch

Download the OpenSSH Portable source code (http://www.openssh.com/portable.html).
Then copy the patch into the OpenSSH folder and apply it. Finally, build
OpenSSH per the normal process.

```bash
$ patch --dry-run < sshlog.patch
$ patch < sshlog.patch
$ ./configure
$ make
$ sudo make install
```

## Example sshlog entries in /var/log/auth.log

```bash
Apr 12 08:49:55 x6 sshd[23775]: sshlog: root ~ritup2HD! 116.31.116.6 1492001395
Apr 12 08:49:56 x6 sshd[23775]: sshlog: root [n0rd574r] 116.31.116.6 1492001396
Apr 12 08:49:56 x6 sshd[23775]: sshlog: root zzzzzzzzzz 116.31.116.6 1492001396
```

## Notes

    * To avoid logging legitimate user connections, use ssh keys.

