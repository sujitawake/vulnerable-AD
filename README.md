<h1 align="center">
  Vulnerable-AD
  <br>
</h1>

Create a vulnerable active directory that's allowing you to test most of active directory attacks in local lab

### Main Features
- Randomize Attacks
- Full Coverage of the mentioned attacks
- you need run the script in DC with Active Directory installed 
- Some of attacks require client workstation
  
### Supported Attacks
- Abusing ACLs/ACEs
- Kerberoasting
- AS-REP Roasting
- Abuse DnsAdmins
- Password in Object Description
- User Objects With Default password (Changeme123!)
- Password Spraying
- DCSync
- Silver Ticket
- Golden Ticket 
- Pass-the-Hash
- Pass-the-Ticket
- SMB Signing Disabled

### Example
```powershell
# if you didn't install Active Directory yet , you can try 
Install-ADDSForest -CreateDnsDelegation:$false -DatabasePath "C:\\Windows\\NTDS" -DomainMode "7" -DomainName "cs.org" -DomainNetbiosName "cs" -ForestMode "7" -InstallDns:$true -LogPath "C:\\Windows\\NTDS" -NoRebootOnCompletion:$false -SysvolPath "C:\\Windows\\SYSVOL" -Force:$true
# if you already installed Active Directory, just run the script !
[Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bor [Net.SecurityProtocolType]::Tls12
IEX((new-object net.webclient).downloadstring("https://raw.githubusercontent.com/sujit/vulnerable-AD/master/vulnad.ps1"));
Invoke-VulnAD -UsersLimit 50 -DomainName "lab.local"
```

### Script output

```
PS C:\Users\Administrator> [Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bor [Net.SecurityProtocolType]::Tls12
PS C:\Users\Administrator> IEX((new-object net.webclient).downloadstring("https://raw.githubusercontent.com/sujit/vulnerable-AD/master/vulnad.ps1"));
PS C:\Users\Administrator> Invoke-VulnAD -UsersLimit 50 -DomainName "lab.local"
        [*] Creating dorri.gabbey User
        [*] Creating lynnet.odele User
        [*] Creating effie.karrie User
        [*] Creating corine.anjanette User
        [*] Creating susi.adella User
        [*] Creating gabey.brittne User
        [*] Creating olva.gwen User
        [*] Creating blisse.ardine User
        [*] Creating elfreda.kenton User
        [*] Creating bell.arlinda User
        [*] Creating concordia.gayle User
        [*] Creating gisele.audrie User
        [*] Creating marti.alyssa User
        [*] Creating ag.linette User
        [*] Creating lefty.agnes User
        [*] Creating celina.lurline User
        [*] Creating darla.celestyn User
        [*] Creating noelyn.grethel User
        [*] Creating fallon.kathrine User
        [*] Creating justine.kelsi User
        [*] Creating susi.dorena User
        [*] Creating janaye.hana User
        [*] Creating madalyn.susi User
        [*] Creating chere.ann User
        [*] Creating dolorita.elsy User
        [*] Creating joanna.lind User
        [*] Creating marilyn.stafani User
        [*] Creating odella.mame User
        [*] Creating amalita.emili User
        [*] Creating frank.sidoney User
        [*] Creating jeannette.raven User
        [*] Creating bertha.erda User
        [*] Creating oralia.christabel User
        [*] Creating cornelia.mireille User
        [*] Creating mandy.dody User
        [*] Creating ilise.mignon User
        [*] Creating liza.cindi User
        [*] Creating ophelia.atalanta User
        [*] Creating kacy.janice User
        [*] Creating lori.pierrette User
        [*] Creating jacklin.aggi User
        [*] Creating page.lind User
        [*] Creating corrina.rebecca User
        [*] Creating beret.shane User
        [*] Creating jillene.christel User
        [*] Creating nessa.darleen User
        [*] Creating flory.ava User
        [*] Creating collette.kimberli User
        [*] Creating gennie.kessia User
        [*] Creating luce.elisa User
        [+] Users Created
        [*] Creating Office Admin Group
        [*] Adding bell.arlinda to Office Admin
        [*] Adding olva.gwen to Office Admin
        [*] Adding oralia.christabel to Office Admin
        [*] Adding marilyn.stafani to Office Admin
        [*] Adding chere.ann to Office Admin
        [*] Creating IT Admins Group
        [*] Adding fallon.kathrine to IT Admins
        [*] Adding flory.ava to IT Admins
        [*] Adding ilise.mignon to IT Admins
        [*] Adding olva.gwen to IT Admins
        [*] Creating Executives Group
        [*] Adding justine.kelsi to Executives
        [*] Adding elfreda.kenton to Executives
        [*] Adding fallon.kathrine to Executives
        [*] Adding marti.alyssa to Executives
        [*] Adding flory.ava to Executives
        [*] Adding page.lind to Executives
        [*] Adding odella.mame to Executives
        [*] Adding ophelia.atalanta to Executives
        [+] Office Admin IT Admins Executives Groups Created
        [*] Creating Senior management Group
        [*] Adding jillene.christel to Senior management
        [*] Adding lynnet.odele to Senior management
        [*] Adding cornelia.mireille to Senior management
        [*] Adding elfreda.kenton to Senior management
        [*] Adding luce.elisa to Senior management
        [*] Adding dolorita.elsy to Senior management
        [*] Adding lori.pierrette to Senior management
        [*] Adding amalita.emili to Senior management
        [*] Creating Project management Group
        [*] Adding gisele.audrie to Project management
        [+] Senior management Project management Groups Created
        [*] Creating marketing Group
        [*] Adding liza.cindi to marketing
        [*] Adding chere.ann to marketing
        [*] Adding concordia.gayle to marketing
        [*] Creating sales Group
        [*] Adding liza.cindi to sales
        [*] Adding ophelia.atalanta to sales
        [*] Adding cornelia.mireille to sales
        [*] Creating accounting Group
        [*] Adding concordia.gayle to accounting
        [+] marketing sales accounting Groups Created
        [*] BadACL GenericAll marketing to Senior management
        [*] BadACL GenericWrite accounting to Senior management
        [*] BadACL WriteOwner sales to Senior management
        [*] BadACL WriteDACL marketing to Senior management
        [*] BadACL Self marketing to Project management
        [*] BadACL WriteProperty marketing to Senior management
        [*] BadACL GenericAll Senior management to Executives
        [*] BadACL GenericWrite Senior management to Office Admin
        [*] BadACL WriteOwner Project management to Executives
        [*] BadACL WriteDACL Senior management to Executives
        [*] BadACL Self Senior management to Executives
        [*] BadACL WriteProperty Senior management to IT Admins
        [*] BadACL WriteProperty marti.alyssa and sales
        [*] BadACL WriteProperty susi.adella and accounting
        [*] BadACL WriteProperty noelyn.grethel and IT Admins
        [*] BadACL WriteOwner lori.pierrette and Senior management
        [*] BadACL GenericAll dorri.gabbey and Project management
        [*] BadACL WriteDACL odella.mame and Project management
        [*] BadACL GenericWrite amalita.emili and IT Admins
        [+] BadACL Done
        [*] Kerberoasting http_svc httpserver


DistinguishedName : CN=http_svc,CN=Managed Service Accounts,DC=lab,DC=local
Enabled           : True
Name              : http_svc
ObjectClass       : msDS-ManagedServiceAccount
ObjectGUID        : b9d4d8c9-fc8d-4341-9373-a87de02bdef9
SamAccountName    : http_svc$
SID               : S-1-5-21-1815723666-3108362439-3967060310-1172
UserPrincipalName :

        [*] Creating mssql_svc services account
DistinguishedName : CN=mssql_svc,CN=Managed Service Accounts,DC=lab,DC=local
Enabled           : True
Name              : mssql_svc
ObjectClass       : msDS-ManagedServiceAccount
ObjectGUID        : b3911d9d-4a22-446b-9056-755de9c49152
SamAccountName    : mssql_svc$
SID               : S-1-5-21-1815723666-3108362439-3967060310-1173
UserPrincipalName :

        [*] Creating exchange_svc services account
DistinguishedName : CN=exchange_svc,CN=Managed Service Accounts,DC=lab,DC=local
Enabled           : True
Name              : exchange_svc
ObjectClass       : msDS-ManagedServiceAccount
ObjectGUID        : 642615ab-f598-44d7-886c-05e4e693f8b8
SamAccountName    : exchange_svc$
SID               : S-1-5-21-1815723666-3108362439-3967060310-1174
UserPrincipalName :

        [+] Kerberoasting Done
        [*] AS-REPRoasting blisse.ardine
        [*] AS-REPRoasting nessa.darleen
        [+] AS-REPRoasting Done
        [*] DnsAdmins : dorri.gabbey
        [*] DnsAdmins : beret.shane
        [*] DnsAdmins Nested Group : Senior management
        [+] DnsAdmins Done
        [+] Password In Object Description Done
        [+] Default Password Done
        [*] Same Password (Password Spraying) : darla.celestyn
        [*] Same Password (Password Spraying) : lynnet.odele
        [+] Password Spraying Done
        [*] Giving DCSync to : dorri.gabbey
        [+] DCSync Done
        [+] SMB Signing Disabled


PS C:\Users\Administrator>
```

### TODO
- Play with workstations !
- Click close issue button on github
