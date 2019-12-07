# domainkey
domainkey for qmail

I tried to support 2048bit DKIM.

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
