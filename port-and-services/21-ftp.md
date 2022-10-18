---
description: >-
  The File Transfer Protocol is a standard communication protocol used for the
  transfer of computer files from a server to a client on a computer network.
---

# 21 - FTP

## general in ftp

```bash
nmap -p21 --script=ftp-* $IP   # auto recon with nmap
ftp $IP                        # anon login
> anonymous
> anonymous
```

## ftp brute-force

```bash
hydra -L /wordlists/users.txt -P /wordlists/password.txt $IP ftp
nmap -p21 --script=ftp-brute --script-agrs userdb=/wordlists/users.txt $IP
```
