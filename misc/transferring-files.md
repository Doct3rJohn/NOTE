# Transferring files

## Impacket

Impacket is a collection of Python classes for working with network protocols.

### SMBserver.py

```bash
smbserver.py <SHARE> /path/to/tranfer
```

<figure><img src="../.gitbook/assets/run-the-python-smbserver.png" alt=""><figcaption><p>Running the python smbserver</p></figcaption></figure>

```bash
copy \\$IP\<SHARE>\file.exe
```

<figure><img src="../.gitbook/assets/copy-file-from-linux-into-windows-smb.png" alt=""><figcaption><p>Transferring files with SMB</p></figcaption></figure>

## References

* [https://blog.ropnop.com/transferring-files-from-kali-to-windows/#smb](https://blog.ropnop.com/transferring-files-from-kali-to-windows/#smb)
