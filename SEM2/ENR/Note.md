
# Switch

## Basic
1. Create Cisco `1 PC` and `1 switch`
2. Connect Switch and PC using console cable (console - RS 232)
3. Go to PC and open terminal (ok and continue)
4. It connect in switch directly
```
[Basic commands]

connect: Open a terminal connection
disable: Turn off privileged commands
disconnect: Disconnect an existing network connection
enable: Turn on privileged commands
exit: Exit from the EXEC
logout: Exit from the EXEC
ping: Send echo messages
resume: Resume an active network connection
show: Show running system information
ssh: Open a secure shell client connection
telnet: Open a telnet connection
terminal: Set terminal line parameters
traceroute Trace route to destination
```

## Privileges
- switch> `enable`  #'can use both `enable` and `en` commands'
### Change date
- check date
	- switch# `show date` 
- set date
	-  switch# `clock set 15:00:00 1 jan 2035`

### Config configuration
- Check switch Current config using command
	- `show running-config`
- Enter global configuration
	- `configure terminal` or `conf t`
#### Change hostname
- switch# `configure terminal`
- switch(config)# `host "NewName"`
#### Secure access to the console line
- switch> `enable`
- switch# `configure terminal`
- switch(config)# `line console 0`
- switch(config)# `password "NewPasswdForLogin"`
- switch(config)# `login`   #'to enable login password request'
- switch(config)# `exit`
#### Secure Privileged mode access
- switch> `enable`
- switch# `configure terminal`
- switch(config)# `enable password "NewPasswdForEn"`
- switch(config)# `exit`
#### Configure an encrypted password to secure access to privileged mode
- switch> `enable`
- switch# `configure terminal`
- switch(config)# `enable secret "NewPasswdForEn"`
- switch(config)# `exit`

#### encrypt all passwords
- switch> `enable`
- switch# `configure terminal`
- switch(config)# `service password-encryption`
- switch(config)# `exit`
- switch# `show running-config` #'`show run'

#### configure a Massege Of The Day (MOTD) banner
- switch> `enable`
- switch# `configure terminal`
- switch(config)# `banner motd ”WelcomeMsgYouWant”`
- switch(config)# `exit`

#### Save and Verify configuration file
- switch> `enable`
- switch# `copy running-config startup-config`


## Implement basic connectivity

| S1  | 192.168.1.253 | 255.255.255.0 |
| --- | ------------- | ------------- |
| S2  | 192.168.1.254 | 255.255.255.0 |
| PC1 | 192.168.1.1   | 255.255.255.0 |
| PC2 | 192.168.1.2   | 255.255.255.0 |
- connect all PC and switch into network 
- set PC IP address 
- connect switch via cli
- then setup ip
	- switch> `en`
	- switch# `conf t`
	- switch(config)# `interface vlan 1` #'`int vlan 1` also work'
	- switch(config-if)# `ip address 10.10.1.1 255.255.255.0` #'`ip addr 10.10.1.1 255.255.255.0`'
	- switch(config-if)# `no shutdown` #'`no shut` also work'



## Router
Basic router configuration

Verify the default router configuration
1. Establish a console connection to R1 (1941 Router)
	1. Choose a console cable from the available connections 
	2. Click PC A and select RS232 port 
	3. Click R1 and select console
	4. Go-to PC A and then desktop tab and terminal
	5. Press enter your now and to configure R1
2. Enter privilege mode and examine the current configuration
	Router> `enable`  #'can use both `enable` and `en` commands'

Configure and Verify initial router configuration
1. Configure the Initial setting on R1
	1. Configure the R1 as host name
	2. Configure motd text "Unauthorized access is strictly prohibited"
	3. Encrypt all plain text passwords. Use Following passwords
		1. Unencrypted : Cisco
		2. Encrypt: it's a secret
		3. Console: letmein
2. Verify the Initial settings on r1
3. Save the configuration file to NVRAM



Connect Router to a local area network 

| Device | Interface   | IP address      | Subnet mask     | Default gateway |
| ------ | ----------- | --------------- | --------------- | --------------- |
| R1     | G0/0        | 192.168.10.1    | 255.255.255.0   | N/A             |
| R1     | G0/1        | 192.168.11.1    | 255.255.255.0   | N/A             |
| R1     | S0/0/0(DCE) | 209.165.200.225 | 255.255.255.252 | N/A             |
|        |             |                 |                 |                 |
| R2     | G0/0        | 10.1.1.1        | 255.255.255.0   | N/A             |
| R2     | G0/1        | 10.1.2.1        | 255.255.255.0   | N/A             |
|        | S0/0/0(DCE) | 209.165.200.226 | 255.255.255.252 | N/A             |
|        |             |                 |                 |                 |
| PC1    | NIC         | 192.168.10.10   | 255.255.255.0   | 192.168.10.1    |
| PC2    | NIC         | 192.168.11.10   | 255.255.255.0   | 192.168.11.1    |
| PC3    | NIC         | 10.1.1.10       | 255.255.255.0   | 10.1.1.1        |
| PC4    | NIC         | 10.1.2.10       | 255.255.255.0   | 10.1.2.1        |

1. Lable all the IP address and network address
2. Add IP address and default gateways to PC
3. Add host names to all switches 
4. Add host names to all routers 
5. Connect relevant IP address to R1
6. Ping PC 1 with PC 2 
7. Connect relevant IP address to router 2
8. Ping PC 3 with PC 4
9. Connect R2 with R1
10. Connect R1 with R2
11. Try to connect PC 1 with PC 4
12. Set the static route to R1
13. Set the static route to R2
14. Connect PC 1 and PC 4 




