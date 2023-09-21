#Enum4linux groups
```
enum4linux -u USERNAME -p PASSWORD -w DOMAIN -G DC_IP_ADDR
```
Users too.

Output to file either std redir or tee to a file.


cme smb IP-Address-DC -u 'ntaadmin' -p 'Password' -X 'get-adfinegrainedpasswordpolicy -filter *'
