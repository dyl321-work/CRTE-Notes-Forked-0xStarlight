# PowerView Enumeration
## Get current domain
#### PowerView
```powershell
Get-NetDomain
```
### AD Module
```powershell
Get-ADDomain
```

## Get object of another domain
### PowerView
```poweshell
Get-NetDomain -Domain moneycorp.local
```
### AD Module
```powershell
Get-ADDomain -Identity moneycorp.local
```

## Get domain SID for the current domain
### PowerView
```powerhshell
Get-DomainSID
```
### AD Module
```powershell
(Get-ADDomain).DomainSID
```

## Get domain policy for the current domain
### PowerView
```powershell
Get-DomainPolicy
(Get-DomainPolicy)."system access"
```
### AD Module
```powershell

```

## Get domain policy for another domain
### PowerView
```powershell
(Get-DomainPolicy -domain moneycorp.local)."system access"
(Get-DomainPolicy -domain moneycorp.local)."kerberos policy"
(Get-DomainPolicy -domain moneycorp.local)."Privilege Rights"
# OR
(Get-DomainPolicy)."KerberosPolicy" #Kerberos tickets info(MaxServiceAge)
(Get-DomainPolicy)."SystemAccess" #Password policy
(Get-DomainPolicy).PrivilegeRights #Check your privileges
```
### AD Module
```powershell

```

## Get domain controllers for the current domain
### PowerView
```powershell
Get-NetDomainController
```
### AD Module
```powershell

```

## Get domain controllers for another domain
### PowerView
```powershell
Get-NetDomainController -Domain moneycorp.local
```
### AD Module
```powershell

```

## Get a list of users in the current domain
### PowerView
```powershell
Get-NetUser
Get-NetUser -Username student1
```
### AD Module
```powershell

```

## Get list of all properties for users in the current domain
### PowerView
```powershell
Get-UserProperty
Get-UserProperty -Properties pwdlastset,logoncount,badpwdcount
Get-UserProperty -Properties logoncount
Get-UserProperty -Properties badpwdcount
```
### AD Module
```powershell

```

## Search for a particular string in a user's attributes
### PowerView
```powershell
Find-UserField -SearchField Description -SearchTerm "built"
```
### AD Module
```powershell

```

## Get a list of computers in the current domain
### PowerView
```powershell
Get-NetComputer
Get-NetComputer -OperatingSystem "*Server 2016*"
Get-NetComputer -Ping
Get-NetComputer -FullData
```
### AD Module
```powershell

```


## Get all the groups in the current domain
### PowerView
```powershell
Get-NetGroup
Get-NetGroup -Domain <targetdomain>
Get-NetGroup -FullData
Get-NetComputer -Domain
```
### AD Module
```powershell

```

## Get all groups containing the word "admin" in group name
### PowerView
```powershell
Get-NetGroup *admin*
Get-NetGroup -GroupName *admin*
Get-NetGroup *admin* -FullData
Get-NetGroup -GroupName *admin* -Doamin moneycorp.local
```
### AD Module
```powershell

```

## Get all the members of the Domain Admins group
### PowerView
```powershell
Get-NetGroupMember -GroupName "Domain Admins" -Recurse
#test the below command
#Get-NetGroupMember -GroupName "Domain Admins" -Properties * | select DistinguishedName,GroupCategory,GroupScope,Name,Members
```
### AD Module
```powershell

```

## Get the group membership for a user
### PowerView
```powershell
Get-NetGroup -UserName "student1"
```
### AD Module
```powershell

```

## List all the local groups on a machine (needs administrator privs on non-dc machines) 
### PowerView
```powershell
Get-NetLocalGroup -ComputerName dcorp-dc.dollarcorp.moneycorp.local -ListGroups
```
### AD Module
```powershell

```

## Get members of all the local groups on a machine (needs administrator privs on non-dc machines)
### PowerView
```powershell
Get-NetLocalGroup -ComputerName dcorp-dc.dollarcorp.moneycorp.local -Recurse
```
### AD Module
```powershell

```

## Get actively logged users on a computer (needs local admin rights on the target)
### PowerView
```powershell
Get-NetLoggedon -ComputerName dcorp-dc.dollarcorp.moneycorp.local 
```
### AD Module
```powershell

```

## Get locally logged users on a computer (needs remote registry on the target - started by-default on server OS)
### PowerView
```powershell
Get-LoggedonLocal -ComputerName dcorp-dc.dollarcorp.moneycorp.local 
```
### AD Module
```powershell

```
 
## Get the last logged user on a computer (needs administrative rights and remote registry on the target)
### PowerView
```powershell
Get-LastLoggedon -ComputerName <servername>
```
### AD Module
```powershell

```

## Find shares on hosts in current domain.
### PowerView
```powershell
Invoke-ShareFinder -Verbose
```
### AD Module
```powershell

```

## Find sensitive files on computers in the domain
### PowerView
```powershell
Invoke-FileFinder -Verbose
```
### AD Module
```powershell

```

## Get all fileservers of the domain
### PowerView
```powershell
Get-NetFileServer
```
### AD Module
```powershell

```
