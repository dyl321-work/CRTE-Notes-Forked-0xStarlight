# SOAPHound is known to be quieter and more op-sec friendly than BloodHound/SharpHound as it avoids LDAP. It uses ADWS instead
## 
```
SOAPHound.exe --buildcache -c C:\AD\Tools\cache.txt
```
```
SOAPHound.exe -c C:\AD\Tools\cache.txt --bhdump -o C:\AD\Tools\bloodhound-output --nolaps
#LAPS is known to be broken for SOAPHound, so we remove it's search using the -nolaps flag

```

    ○ Newer and more op-sec friendly as it avoids LDAP all-together. It uses ADWS instead of LDAP.
		○ Works by building a cache of work-domain objects, such as SID's and distinguished names of users, groups, GPO's, and other domain objects.
		○ It talks to Active Directory Web Services (ADWS - Port 9389) in place of sending LDAP queries - just like the AD Module.
			§ Almost no network-based detection (like MDI).
			§ It retrieves information about all objects (objectGuid=*) and then process them.It means limited LDAP queries - less chance of endpoint detection.
		○ Build a cache that includes basic info about domain objects.
		SOAPHound.exe --buildcache -c C:\AD\Tools\cache.txt
		○ Collect BloodHound compatible data
		SOAPHound.exe -c C:\AD\Tools\cache.txt --bhdump -o C:\AD\Tools\bloodhound-output --nolaps
#LAPS is known to be broken for SOAPHound, so we remove it's search using the -nolaps flag
