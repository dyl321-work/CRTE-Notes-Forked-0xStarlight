# Foreign Security Principals (FSPs) - Used in Cross-Forest attacks
## Enumerate Foreign Users
##### PowerView
```powershell
Find-ForeignUser
```
##### AD Module
```powershell
Get-ADObject -Filter {ObjectClass -eq "foreignSecurityPrincipal"}
```

## Enumerate Foreign Groups
##### PowerView
```powershell
Find-ForeignGroup
```
##### AD Module
```powershell
Get-ADObject -Filter {ObjectClass -eq "foreignSecurityPrincipal"}
```

## Full FSP Enumeration
##### PowerView
```powershell
Find-ForeignUser -Verbose
Find-ForeignGroup -Verbose
```
##### AD Module
```powershell
Get-ADObject -Filter {ObjectClass -eq "foreignSecurityPrincipal"} -Properties *
```
