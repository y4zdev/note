# Install Windows 7 As Client

1. Create as new folder and rename it as **VWS**.
2. Inside **VWS** Folder create another new folder and rename it as Windows 7.
3. Inside **VWS** Folder create another new folder and rename it as Windows server 2012.
4. open VMware workstation.
5. Create new virtual machine and select installer disk image file iso and brows to where your iso image disk locate
6. Personalized Windows 7 pick the username and password. 
7. choose a location for your virtual machine you can simply accept the defiant and move forward to the installation
8. click default and accept the default. 
9. click ok and finish and Windows 7 begin to load. 
10. After Windows 7 started set the network location as public location. 
11. Add computer icon, network icon, account icon and computer panel icon too the desktop
12. open network and sharing center go-to advanced sharing settings turn on network discovery, file and printer sharing and public folder sharing
13. go-to the system and security and control panel and turn off the windows firewall
14. go-to the system and security on control panel and distance Windows updates.
15. go-to hardware and sound in the control panel go-to the power option and then edit plan settings select the option never in the turn off display. 
16. set sound profile to no sound.
17. disable the auto play
18. change the background color to solid color
19. unpin the windows media player from the task bar
20. go-to program and features in the control panel select turn Windows features on our off 
    1. UNTICK internet printing client
    2. TICK  - RIP listener
    3. TICK - Simple TCPIP server
    4. UNTICK - Tablet of component
    5. TICK - Telnet Client 
    6. TICK - TFTP Client 
    7. UNTICK - Windows Gaffney platform
    8. UNTICK - XPS viewer
    9. UNTICK - XPS services
21. Restart and loving to the windows again. 
22. Go-to VM and take screenshot name it as '**original**' wait for it to save 100%.
23. Go-to the network adapter in the bottom bar click settings select '**HOST-only**' and click ok.
24. Go-to the command prompt from the start menu and type the command '**ipconfig**' and check the IP
25. suspended Windows 7 from the top bar


# Install Windows 12 As Server

1. create new virtual machine and select installer disk file iso and brows to where your windows 2012 disk file
2. personalized Windows 2012 with username and password
3. choose as location for your virtual machine you can simply accept the default and move forward in the installation. 
4. click next and accept the default disk size.
5. click ok and finish and Windows 2012 begins to load
6. add computer icon, network icon, account icon and control panel to the desktop
7. open network and sharing center go-to advanced sharing settings turn on network discovery. 
8. go-to the system and security on control panel and turn off the Windows firewall
9. go-to the system and security on control panel and disable windows updates. 
10. go-to hardware and sound in the control panel , go-to the power option and then edit plan settings, select the option never in the turn off display. 
11. set sound profile to no sound
12. disable the auto play
13. go-to program and features in the control panel select turn Windows features on or off
    1. TICK - Client for NFS
    2. TICK - Direct Play
    3. TICK - Simple TCPIP services 
    4. TICK - Telnet Client
    5. TICK - Telnet server
    6. TICK - TFTP Client 
14. Start the services on the local server manager. 
15. go-to book and take snap shot name it as '**Original**' wait it for save 100%.
16. go-to the network adapter click settings select host only click ok
17. go-to the command prompt on the start menu and type the command '**ipconfig**' and check the IP address, client and server IP address should be in the same network. 
18. suspended Windows 2012 from the top bar

# promoting domain controller on Windows server
1. go-to the server 2012
2. Rename the PC to "WinServer2012"
3. go-to the windows 7 and rename the PC as "Windows7"
4. After restarting login to the server using "Ctrl+Alt+Insert"
5. Add a computer description to the client PC as "Windows 7 Client PC" 
6. Add a computer description to server PC as "Windows Server 2012"
7. Confirm the two PCs are in the same Network
8. go-to the server manager in server PC and select "active directory domain services" then install.
9. Add a new forest in promote this server to domain controller
10. at the root domain name as "winadserver.net"
11. go-to the computer management in tools from the top right corner and then local users and groups and then  give a strong password to the administrator and set the password.
12. install active domain services server PC will be restarted after the restarted
13. logon to the server PC again
14. go to the dns section in server manager and check the IP address
15. at that dns ip address to the client PC
    1. go-to the properties in the network in client PC
    2. go-to change adopter settings
    3. go-to the properties in local area connection
    4. double click on internet protocol v4 "(TCP/IP4)"
    5. select the dns server address
    6. add the dns ip address in the box
    7. click disable in local area connection and enable again
    8. go-to the status in local area connection and go-to the details and check up v4 dns address

# Join Windows 7 active domain
1. go-to the properties in computer in client PC and then advanced system settings then go-to change in computer name select member of domain in their type the dns server name "winadserver" (same root domain name in server PC)
2. give the username and the password
3. welcome message will pop up
4. restart the PC
5. check the domain
6. go back to the server PC
7. go to the tools from top right corner
8. select active directory users and computers
9. expand win adserver.net select computers check the client PC their
10. go-to the properties of that client PC then check the domain details
11. go-to the VM and take snapshot in server PC name it as "AD-DS/DNS Installed" wait for it to save 100% 
12. go-to VM and take snapshot in client Pc name it as "Domain Joint" wait for it save 100%

# Group Users SharedFolders policies
1. add "a group active directory users and computers" In the server manager in server pc
2. give a group name as "networking"
3. add a new user and give first name as "Jason" initial as "S" and last name as "Denzil"
4. give the user logon name as "Jasond"
5. give a temporary password
6. at the user Jason to the group networking
7. double click networking group and check the members "User json should be their" 
8. add the administrator to the member of section
9. create a new folder as "shared data" in local disk c
10. create another new folder inside that folder and name it as "networking"
11. share the folder from the properties of that folder
12. limit the number of simultaneously users to 20
13. remove the permission of "everyone"
14. allow full control and charge to the group networking 
15. go-to the active directory and users and computers from the tools in the server manager
16. select "L" from the profile section in user Jason properties 
17. go-to networking folder and copy the network cards and then paste it in user Jason properties
18. charge the path with DNS ip address 
19. select "create a GPO I in this domain and link it here" in win add server.net inside group policy management
20. give the name as "UserRestrictions"
21. edit the "UserRestrictions"
22. go-to the user configuration expand the policies and then expand the administrative template and go to all settings. 
23. from ware enable the "hide internet explorer icon from the desktop"
24. remove a documents icon from star menu 
25. enable "remove game link from start menu"
26. login again with the username as Jasond and given password
27. login with a new password
28. add desktop icons to the desktop
29. take snapshot give a name as "GROUP-USERS-SHAREDFOLDERS-POLICIES" server PC and client PC.