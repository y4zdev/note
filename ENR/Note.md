
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
