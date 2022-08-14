# 01 Installing the Domain Controller

1. Use `sconfig` to:

    - Change the hostname
    - Change the IP Address to static
    - Change the DNS server to our own IP address

2. Install the Active Directory Windows Feature

```shell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

```shell
Get-NetIPAddress
Get-ClientDNSServerAddresses
Set-ClientDNSServerAddresses -Interface 4 -ServerAddresses
```
# Joining the workstation for the domain

```shell
Add-Computer -DomainName xyz.com -Credential xyz\Administrator -Force -Restart
```
