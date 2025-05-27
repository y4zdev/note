
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





## IPv4 Addressing
- IPv4 (Internet Protocol version 4) is the fourth revision of the Internet Protocol.
- It uses a 32-bit address scheme, typically represented in dotted-decimal notation (e.g.. 192.168.1.1).
- IPv4 supports approximately 4.3 billion unique addresses, which are divided into classes (A, B, C) and reserved ranges.
### Find the error, if any, in the following IPv4 addresses.
1. 111.56.045.78 - Can't use 0 
2. 221.34.7.8.20 - more that 4 decimal points
3. 75.45.301.14 - 3rd number outside of 0-255 range
4. 11100010.23.14.67 - mix of binary and decimal 

![[IMG20250520102433.jpg]]


### A block of addresses is granted to a small organization. We know that one of the addresses is 205.16.37.39/28,
1. What is the first address in the block? **205.16.37.32**
2. What is the first usable address in the block? **240.16.37.33**
3. What is the last address in the block? **205.16.37.47**
4. What is the last usable address in the block? **205.16.37.46**
5. How many addresses are in the block? **15**
![[IMG20250520113551.jpg]]



### Find the class of each address.

a. 00000001 00001011 00001011 11101111 = class A
b. 11000001 10000011 00011011 11111111 = class C
c. 14.23.120.8 = class A
d. 252.5.15.111 Class =E

1. What are the two main components of the IP address? 
	- **Network ID**
	- **Host ID**
2. In as block of address we know the IP address of one host is 25.34.12.56/16
	1. What's is network address 
		- **25.34.0.0/16**
	2. First useable address
		- **25.34.0.1**
	3. Last usable address in the block
		- **25.34.255.254**
3. Find out which of the following address below to the same network
	-  [x] 123.4.6.2.
	-  [x] 123.4.78.9
	-  [ ] 132.14.56.12
	-  [x] 123.4.0.0
	
	-  [x] 10.0.0.1
	-  [x] 10.1.1.1
	-  [x] 10.1.2.2.
	-  [ ] 11.0.0.1
	
	-  [ ] 172.16.16.16  
	-  [ ] 172.17.16.16
	-  [x] 173.16.16.16
	-  [x] 173.16.16.20
4. Find the usable range of address in following blocks
	1. 123.56.77.32/29
		- 123.56.77.33-123.56.77.38
	2. 200.17.21.128/27
		- 200.17.21.129-200.17.21.158
	3. 17.34.16.0/23
		- 17.34.16.1-17.34.17.254
	4. 180.34.64.64/30
		- 180.34.64.65-180.34.64.67

## Sub netting 

Your given the Network address 175.200.0.0/24 your required to have 4 subnets. What is the minimum number of host bits you can take into the Network bits for this purpose.
Write down the network address for 4 subnets Write the subnet mask for the network
	Subnet 1 :   175.200.0.0/26 - 175.200.0.63/26
	Subnet 2 :   175.200.0.64/26 - 175.200.0.127/26
	Subnet 3 :   175.200.0.128/26 - 175.200.0.191/26
	Subnet 4 :   175.200.0.192/26 - 175.200.0.255/26




 ![[IMG20250520150211.jpg]]



As system administrator you have to create 5 subnet using IP block 192.168.2.0/24 write down the network and broadcast address with subnet mask in each Subnets

Subnet1 : 192.168.2.0/27 - 192.168.2.31/27
Subnet2 : 192.168.2.32/27 - 192.168.2.63/27
Subnet3 : 192.168.2.64/27 - 192.168.2.95/27
Subnet4 : 192.168.2.96/27 - 192.168.2.127/27
Subnet5 : 192.168.2.128/27 - 192.168.2.159/27


As system administrator you have to create 10 Subnets using the IP block 192.168.2.0/24 write down the first useable IP address with subnet mask in each subnet 

Subnet : 192.168.2.1/28
Subnet : 192.168.2.17/28
Subnet : 192.168.2.33/28
Subnet : 192.168.2.49/28
Subnet : 192.168.2.65/28
Subnet : 192.168.2.81/28
Subnet : 192.168.2.97/28
Subnet : 192.168.2.113/28
Subnet : 192.168.2.129/28
Subnet : 192.168.2.145/28

## Variable Length subnet making

#### ABC corporation has 200 computers crucified on to 4 department, Sales, accounting, hr, and audit. The computer are devided into department as follow
- Sales: **100PCS**
- Accounting: **50PCS**
- Hr: **25PCS**
- Audit: **25PCW**
Your results to build subnets to for the about department and Have been assign class C network address **192.168.1.0** to do so determine the minimal number of host bits that should be incorporated in to the network bits for this purpose and write the network address and subnet mask for each department.
![[IMG20250522101213.jpg]]


#### As system administrator you have 3 network with 25,58,45 computers using the IP block 10.20.30.0/24 write down first and last usable IP address in search subnet

10.20.30.0/24

Network 1: 10.20.30.1/26 - 10.20.30.62/26
Network 2: 10.20.30.65/26 - 10.20.30.126/26
Network 3: 10.20.30.129/27 - 10.20.30.158/27


As system administrator you have 6 network with 25,58,10,12,5,45 computers using the IP block 10.20.30.0/24 write down first and last usable IP address in each subnet

10.20.30.0/24
58,45,25,12,10,5

Network 1: 10.20.30.1/26 - 10.20.30.62/26
Network 2: 10.20.30.65/26 - 10.20.30.126/26
Network 3: 10.20.30.129/27 - 10.20.30.158/27
Network 4: 10.20.30.161/28 - 10.20.30.174/28
Network 5: 10.20.30.177/28 - 10.20.30.190/28
Network 6: 10.20.30.193/29 - 10.20.30.198/29

#### Assign a IP address the following topology using IP block 192.168.10.0/24
![[IMG20250522134827.jpg]]
![[IMG20250522141434.jpg]]


#### Q
![[IMG20250522142317.jpg]]
How many subnets are in there topology ? 8
Assign a IP address each an every topology using IP block 192.168.0.0/24



15,24,28,56,2,2,2,2

4,4,4,4,18,27,31,59


Network1 : 192.168.0.1/26 - 192.168.0.62/26
Network2 : 192.168.0.65/27 - 192.168.0.94/27
Network3 : 192.168.0.97/27 - 192.168.0.126/27
Network4 : 192.168.0.129/27 - 192.168.0.158/27
Network5 : 192.168.0.161/30 - 192.168.0.162/30
Network6 : 192.168.0.165/30 - 192.168.0.166/30
Network7 : 192.168.0.169/30 - 192.168.0.170/30
Network8 : 192.168.0.173/30 - 192.168.0.174/30
![[IMG_20250522_144240.jpg]]


#NEWx