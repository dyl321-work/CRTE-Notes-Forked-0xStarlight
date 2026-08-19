# Used heavily later in the course
## Enumerate gMSAs
##### PowerView
```
Get-DomainObject -LDAPFilter '(objectClass=msDSGroupManagedServiceAccount)'
```
##### AD Module
```
Get-ADServiceAccount -Filter *
```

## Who Can Read the Password?
##### PowerView
```
Get-DomainObject -Identity jumpone -Properties msDS-GroupMSAMembership
```
##### AD Module
```
Get-ADServiceAccount -Identity jumpone -Properties * | select PrincipalsAllowedToRetrieveManagedPassword
```

## Read Password Blob
##### PowerView
```
Get-DomainObject -Identity jumpone -Properties msDS-ManagedPassword
```
##### AD Module
```
Get-ADServiceAccount -Identity jumpone -Properties msDS-ManagedPassword
```
