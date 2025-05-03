# Cisco packet tracer

Getting started with Cisco packet tracer

1. Open Cisco packet tracer 
2. Find the home router from the network component box click it and drag it into the workspace 
3. go to the end devices click and drag PC and Laptop to the work space
4. go to home click and drag a webcam to the workspace 
5. go to delete from main toolbar and delete the webcam from the work space
6. undo the deletion and take back the webcam 
7. go to the connections from network component box and select automatic connection time and connect the router with the PC
8. click on the laptop property window will pop up turn off the laptop from there remove the wire card from the laptop and drag it to the left
9. put the wireless interface (WPC300N) from left side to the laptop. turn on the laptop
10. give the IP address 192.168.1.3 and subnet mask 255.255.255.0
11. give default gateway as 192.168.1.1
12. run up config command on the command prompt of the PC
13. run up config command on the command prompt of the laptop from 

#add old note


# static routing
1. Open "MyPacketTracer" file 
2. Lable every device with their I'll address and default gateway
3. Try to ping Colombo PC with galle and Kandy pc
4. Set static route from Colombo pc to Kandy pc
5. Same way set static route from Colombo pc to Galle pc
6. Same way set static route from Kandy pc to Colombo pc
7. Same way set static route from Kandy pc to Galle pc
8. Same way set static route from Galle pc to Colombo pc
9. Same way set static route from Kandy pc to Galle pc
10. Try to ping Colombo PC with Kandy PC and Galle PC
11. Try to ping Kandy PC with Colombo PC and Galle PC
12. Try to ping Galle PC with Kandy PC and Colombo PC


Static route (Colombo-Kandy)
- Network: 192.168.2.0
- Mask: 255.255.255.0
- Next hop: 192.168.4.2

Static route (Colombo-Galle)
- Network: 192.168.3.0
- Mask: 255.255.255.0
- Next hop: 192.168.5.2

Static route (Kandy-Colombo)
- Network: 192.168.1.0
- Mask: 255.255.255.0
- Next hop: 192.168.4.1

Static route (Kandy-Galle)
- Network: 192.168.3.0
- Mask: 255.255.255.0
- Next hop: 192.168.4.1

Static route (Galle-Colombo)
- Network: 192.168.1.0
- Mask: 255.255.255.0
- Next hop: 192.168.5.1

Static route (Galle-Kandy)
- Network: 192.168.2.0
- Mask: 255.255.255.0
- Next hop: 192.168.5.1