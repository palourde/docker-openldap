# docker-openldap

Build and start openldap
```
docker build -t openldap .
docker run -d -p 389:389 -p 689:689 openldap:latest
docker exec -it 466b504256f3229ffb51ed735fefd036f1f6d0bf1213aa366fb1eac341502cd3 ldapsearch -x -H ldap://localhost -b dc=acme,dc=org -D "cn=admin,dc=acme,dc=org" -w P@ssw0rd!
```

Start phpLDAPadmin
```
docker run -d -p 6443:443 \
  --env PHPLDAPADMIN_LDAP_HOSTS=docker.local \
  osixia/phpldapadmin:0.7.2
```

Authenticate via phpLDAPadmin with the following information:

URL: https://localhost:6443/  
User: `cn=admin,dc=acme,dc=org`  
Pass: `P@ssw0rd!`  