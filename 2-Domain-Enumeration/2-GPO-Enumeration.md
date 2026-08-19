# GPO
## Get list of GPO in current domain.
##### PowerView
```powershell
Get-NetGPO
Get-NetGPO -ComputerName dcorp-student1.dollarcorp.moneycorp.local
Get-DomainGPO
Get-GPO -All
#(GroupPolicy module)
Get-GPResultantSetOfPolicy -ReportType Html -Path C:\Users\Administrator\report.html
#(Provides RSoP)
gpresult /R /V
#(GroupPolicy Results of current machine)
```
##### AD Module
```
Get-GPO -All
#(Requires **Import-Module GroupPolicy**)
```

## Get GPO(s) which use Restricted Groups or groups.xml for interesting users
##### PowerView
```powershell
Get-NetGPOGroup 
```

## Get users which are in a local group of a machine using GPO
##### PowerView
```powershell
Find-GPOComputerAdmin -ComputerName student1.dollarcorp.moneycorp.local
```

## Get machines where the given user is member of a specific group
##### PowerView
```powershell
Find-GPOLocation -Username student1 -Verbose
```

## Get OUs in a domain
##### PowerView
```powershell
Get-NetOU -FullData
Get-DomainOU
```
##### AD Module
```
Get-ADOrganizationalUnit -Filter *
```

## Find Specific OU
##### PowerView
```powershell
Get-DomainOU -Identity "Servers"
Get-DomainOU -LDAPFilter '(name=*Server*)'
```
##### AD Module
```powershell
Get-ADOrganizationalUnit -Filter 'Name -like "*Server*"'
Get-ADOrganizationalUnit -Identity <DistinguishedName>
```

## Enumerate Objects in an OU
##### PowerView
```powershell
(Get-DomainOU -Identity "<OU Name>").distinguishedname | % { Get-DomainObject -SearchBase $_ } | select name,samaccounttype
Get-DomainObject -SearchBase "OU=Servers,DC=corp,DC=local"
```
##### AD Module
```powershell
Get-ADObject -Filter * -SearchBase "OU=Servers,DC=corp,DC=local"
```

## Enumerate Users in an OU
##### PowerView
```powershell
Get-DomainUser -SearchBase "OU=Servers,DC=corp,DC=local"
```
##### AD Module
```powershell
Get-ADUser -Filter * -SearchBase "OU=Servers,DC=corp,DC=local"
```

## Get GPO applied on an OU. Read GPOname from gplink attribute from Get-NetOU
##### PowerView
```powershell
Get-NetGPO -GPOname "{AB306569-220D-43FF-BO3B-83E8F4EF8081}"
Get-GPO -Guid AB306569-220D-43FF-B03B-83E8F4EF8081
#(GroupPolicy module)
```
