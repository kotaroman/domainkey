# domainkey
domainkey for qmail

I tried to support 2048bit DKIM.  
TXT record for BIND is automatically set to 2 lines.

original shell command  
https://notes.sagredo.eu/files/qmail/domainkey  

Please rewrite according to the environment.
```
#CONFIGDIR="/usr/local/etc/domainkeys"
CONFIGDIR="/var/qmail/control/domainkeys"

# DKIMSIGNOPTIONS="-z 2" is required when 2048 bit
#BIT=1024
BIT=2048

# Number of characters to split
SPLIT=255

# chown -R qmailr.qmail or vpopmail.vchkpw
#CHOWN_USER_GROUP="qmailr.qmail"
CHOWN_USER_GROUP="vpopmail.vchkpw"
```

Set DKIMSIGNOPTIONS to qmail environment variable to support 2048bit.
```
DKIMSIGNOPTIONS="-z 2"
```

Example
```
$ domainkey your-domain.com
Generating RSA private key, 2048 bit long modulus
...................................................+++
.......+++
e is 65537 (0x10001)
writing RSA key

default._domainkey.your-domain.com. IN TXT ("v=DKIM1; k=rsa; t=y; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA1KurraHD53HZfIlaWVg9n6B9nzc7FCxUm7A5Mq8jMS+hP6EABPAQeBqnv3w8AE2/OQ+l5o0y4FLx/GV0HJNMxY+0pdbSTmCbChPo6fqypifwwI8+M2PUCnSKqLW9RR3wHOclL3yfe0npLNQe/roMatnXrndtmXNc8rabjZKmgOarjTxFYt/p5oCzm8Pm"
        "DaE11untfEtCVNyY6JqtZTSv3wUTlZQ1vCfFtGsNWL/0w66m1OxZhkxkPnL2dDux8peZso68pEngzEIVY3pE0b0xudfQSBBsZ/L7knAS99IIVWYbNWwxvveS2uNs6lVLMnLOSlkDhFgQod3ri2qjVcPZnwIDAQAB")
        
```
