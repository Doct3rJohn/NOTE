# Cracking Stuff

## Password dictionaries

* [https://github.com/zacheller/rockyou](https://github.com/zacheller/rockyou)
* [https://github.com/danielmiessler/SecLists/tree/master/Passwords](https://github.com/danielmiessler/SecLists/tree/master/Passwords)
* [https://github.com/danielmiessler/SecLists/tree/master/Passwords/Default-Credentials](https://github.com/danielmiessler/SecLists/tree/master/Passwords/Default-Credentials)
* [https://github.com/danielmiessler/SecLists/tree/master/Passwords/Common-Credentials](https://github.com/danielmiessler/SecLists/tree/master/Passwords/Common-Credentials)
* [https://github.com/rapid7/metasploit-framework/tree/master/data/wordlists](https://github.com/rapid7/metasploit-framework/tree/master/data/wordlists)

### ZIP file

```bash
zip2john file.zip > zip.hash
john --wordlist=/path/wordlist.txt zip.hash
```

### PFX file

```bash
pfx2john file.pfx > pfx.hash
john --wordlist=/path/wordlist.txt pfx.hash

# Extracting the certificate from *.pfx file
openssl pkcs12 -in file.pfx -nocerts -out epriv.key            # Extract the encrypted private key
openssl pkcs12 -in file.pfx -clcerts -nokeys -out pub.cert     # Extract the certificate/public key
openssl rsa -in epriv.key -out dpriv.key                       # Decrypted the private key
```
