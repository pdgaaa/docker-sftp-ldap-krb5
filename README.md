# docker-sftp-ldap-krb5
A mix between https://hub.docker.com/r/turgon37/sftp-ldap and https://hub.docker.com/r/phihos/sssd-krb5-ldap, thanks to them !

```
docker run --name sftp-ldap --env-file ./.env -p 22222:22 -v "/home/user/foo:/data/foo:rw" elyout/sftp-ldap-krb5:latest
```

```
.env

KERBEROS_REALM=DOMAIN-AD.EXT
LDAP_BASE_DN=OU=SITE,OU=ENTITY,DC=DOMAIN-AD,DC=EXT
LDAP_BIND_DN=CN=USER_BIND,OU=SERVICEACCOUNT,DC=DOMAIN-AD,DC=EXT
LDAP_BIND_PASSWORD=`sss_obfuscate -d DOMAIN-AD.EXT`
LDAP_URI=ldap://server.domain-ad.ext
```
