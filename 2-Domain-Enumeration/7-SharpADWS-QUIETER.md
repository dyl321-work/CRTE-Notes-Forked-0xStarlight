# STEALTHY AND SIMILAR TO SOAPHOUND - HOWEVER, MORE FLEXIBLE AND GRANULAR AND CAN SHOW ONLY RELEVANT DATA IF REQUIRED
## 
```
SharpADWS.exe Cache
```
```
SharpADWS.exe Acl {-user,-groups,-groups,-gpo..}
#E.g:
SharpADWS.exe Acl -user > user_acls.txt
#Piping it because the output is quite huge!
```
```
#ACLs for users with rid over 1000 (excludes any defaults system accounts and groups):
SharpADWS.exe Acl -dn "CN=Users, DC=us,DC=techcorp,DC=local" -scope Subtree -rid 1000
```
```
#Users with DCSync rights:
SharpADWS.exe DCSync -list
```
#RID's over 1000 are after the Domain was set-up

		○ Also uses ADWS and builds a cache mapping of each domain object to its SID.
		○ Build a cache that contains mapping of account to sid:SharpADWS.exe Cache
		○ Supports enumerating ACLs, ADCS information, delegations and more:
			§ ACLs:SharpADWS.exe Acl {-user,-groups,-groups,-gpo..}#E.g.SharpADWS.exe Acl -user > user_acls.txt#Piping it because the output is quite huge!#The severity in the Acl that is output shows the chance it can be used for privilege escalation! Ctrl+f and search for 'Critical' severity.
			§ ACLs for users with rid over 1000 (excludes any defaults system accounts and groups):SharpADWS.exe Acl -dn "CN=Users, DC=us,DC=techcorp,DC=local" -scope Subtree -rid 1000
			§ Users with DCSync rights:SharpADWS.exe DCSync -list
RID's over 1000 are after the Domain was set-up
