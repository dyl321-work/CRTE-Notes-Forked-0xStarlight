# Trusts - Current Domain
## Get a list of all domain trusts for the current domain
##### PowerView
```powershell
Get-DomainTrust
#or legacy:
Get-NetDomainTrust
Get-NetDomainTrust -Domain us.dollarcorp.moneycorp.local
```
##### AD Module
```
Get-ADTrust -Filter *
```

## Get details about the current forest
##### PowerView
```powershell
Get-NetForest
Get-NetForest -Forest eurocorp.local
```
##### AD Module
```

```

## Get all domains in the current forest
##### PowerView
```powershell
Get-NetForestDomain
Get-NetForestDomain -Forest eurocorp.local
```

## Get all global catalogs for the current forest
##### PowerView
```powershell
Get-NetForestCatalog
Get-NetForestCatalog -Forest eurocorp.local
```
 
## Map trusts of a forest
##### PowerView
```powershell
Get-NetForestTrust
Get-NetForestTrust -Forest eurocorp.local
```

# Trusts for another Domain and Forest Trusts
## Trusts for Another Domain
##### PowerView
```powershell
Get-DomainTrust -Domain moneycorp.local
```
##### AD Module
```
Get-ADTrust -Server moneycorp.local -Filter *
```

## Forest Trusts
##### PowerView
```powershell
Get-ForestTrust
Get-NetForestTrust
```
##### AD Module
```
Get-ADForest
```
