# User hunting in current Trust
## Find all machines on the current domain where the current user has local admin access
```powershell
Find-LocalAdminAccess -Verbose
```

## Find computers where a domain admin (or specified user/group) has sessions
```powershell
Invoke-UserHunter
Invoke-UserHunter -GroupName "RDPUsers"
```


## To confirm admin access
```powershell
Invoke-UserHunter -CheckAccess
```

## Find computers where a domain admin is logged-in
```powershell
Invoke-UserHunter -Stealth
```

## Find computers where a domain admin (or specified user/group) has sessions
```powershell
Find-DomainUserLocation -Verbose
Find-DomainUserLocation -UserGroupIdentity "StudentUsers"
```

## Find computers where a domain admin session is available and current user has admin access (uses Test-AdminAccess)
```powershell
Find-DomainUserLocation -CheckAccess
```

## Find computers (File Servers and Distributed File servers) where a domain admin session is available.
```powershell
Find-DomainUserLocation –Stealth
```
