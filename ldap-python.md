```python
import pprint

import ldap
from ldap.filter import escape_filter_chars

BINDDN = "cn=read-only-admin,dc=example,dc=com"
BINDPW = "password"
KEYWORD = "boyle"

ldap_conn = ldap.initialize("ldap://ldap.forumsys.com")
ldap_conn.simple_bind_s(BINDDN, BINDPW)


ldap_filter = "(cn=*%s*)" % (ldap.filter.escape_filter_chars(KEYWORD))

ldap_results = ldap_conn.search_s(
    "dc=example,dc=com",
    ldap.SCOPE_SUBTREE,
    ldap_filter,
)

pprint.pprint(ldap_results)
```
### Instalação do python-ldap

```sh
# https://stackoverflow.com/questions/4768446/i-cant-install-python-ldap

$ sudo apt-get install libsasl2-dev python-dev-is-python3 libldap2-dev libssl-dev

```


```text

beautifulsoup4==4.13.4
pyasn1==0.6.1
pyasn1_modules==0.4.2
python-ldap==3.4.4
soupsieve==2.7
typing_extensions==4.13.2
```


