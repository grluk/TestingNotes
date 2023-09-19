#### Basic powershell function to get all users in domain
```
function Get-ADUsers{
  Param($Dom)
  if($Dom){$Dom = [ADSI]"LDAP://$dom"}else{$Dom = [ADSI]""}
  $filter = "(&(objectcategory=user))"
  $searcher = New-Object System.DirectoryServices.DirectorySearcher($Dom,$filter)
  $searcher.pagesize = 1000
  $searcher.findall()
}
Get-AdUsers
```

