---
description: >-
  upgrade the reverse shell is one way to gain full working shell. Such as tab
  completion, CTRL + C, etc.
---

# Upgrade reverse shell

## Python

```bash
# This can be in either python3 or python2.
-> python3 -c 'import pty;pty.spawn("/bin/bash")'
Ctrl + Z [background]
-> stty raw -echo; fg [Enter 2 times]
-> export TERM=xterm
```

## Scripts

```bash
-> script /dev/null -c bash
Ctrl + Z [background]
-> stty raw -echo; fg [Enter 2 times]
-> export TERM=xterm
```
