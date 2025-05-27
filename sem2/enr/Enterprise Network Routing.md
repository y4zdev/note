
## Switch Configuration

### Step 1: Set Up the Physical Topology
1. Open Cisco Packet Tracer.
2. From the device menu:
    - Drag **1 Switch** (e.g., `2960`) onto the workspace.
    - Drag **1 PC** onto the workspace.
3. Use a **Console Cable** to connect:
    - PC `RS232` port → Switch `Console` port.

### Step 2: Access the Switch CLI
1. Click the PC > **Desktop tab** > **Terminal**.
2. Click **OK** to use default terminal settings (9600 baud).
3. The terminal connects directly to the switch CLI.

### Step 3: Basic EXEC Mode Commands
Here are commonly used EXEC mode commands:
```plaintext
connect      : Opens a terminal connection to another device.
disable      : Exits privileged EXEC mode and returns to user EXEC mode.
disconnect   : Terminates a remote terminal session.
enable       : Enters privileged EXEC mode from user EXEC mode.
exit         : Exits the current command mode or session.
logout       : Logs out from the session.
ping         : Sends ICMP echo requests to test network connectivity.
show         : Displays system or interface information.
ssh          : Starts a secure shell (SSH) connection to another device.
telnet       : Starts a Telnet connection to another device.
traceroute   : Traces the path packets take to a destination.
```

### Step 4: Enter Privileged EXEC Mode.
```css
:Switch> enable
```
**Explanation**: This command elevates the user from user EXEC mode (`>`) to privileged EXEC mode (`#`), giving access to advanced configuration and monitoring commands.

### Step 5: Configure System Date and Time
- Check system time:
```css
:Switch# show clock
```
**Explanation**: Displays the current time and date settings of the device.

- Set date and time:
```css
:Switch# clock set 15:00:00 1 Jan 2035
```

**Explanation**: Manually sets the system clock to the specified time and date.

### Step 6: Enter Global Configuration Mode

- View current configuration:
    

```bash
Switch# show running-config
```

**Explanation**: Displays the current configuration running in RAM.

- Enter configuration mode:
    

```bash
Switch# configure terminal
```

**Explanation**: Enters global configuration mode where most device settings can be modified.

### Step 7: Set Hostname

```bash
Switch(config)# hostname CoreSwitch
```

**Explanation**: Changes the device name that appears in the CLI prompt.

### Step 8: Secure Console Access

```bash
CoreSwitch(config)# line console 0
CoreSwitch(config-line)# password letmein
CoreSwitch(config-line)# login
CoreSwitch(config-line)# exit
```

**Explanation**:

- `line console 0`: Accesses the console line configuration.
    
- `password letmein`: Sets a password for console login.
    
- `login`: Enables password checking at console login.
    
- `exit`: Exits to global configuration mode.
    

### Step 9: Secure Privileged EXEC Access

```bash
CoreSwitch(config)# enable password Cisco
CoreSwitch(config)# enable secret itsasecret
```

**Explanation**:

- `enable password Cisco`: Sets a basic (unencrypted) password for entering privileged mode.
    
- `enable secret itsasecret`: Sets an encrypted password that overrides `enable password`.
    

### Step 10: Encrypt All Passwords

```bash
CoreSwitch(config)# service password-encryption
```

**Explanation**: Encrypts all plaintext passwords in the configuration file using a weak encryption.

- Verify encryption:
    

```bash
CoreSwitch# show running-config
```

**Explanation**: View encrypted password entries.

### Step 11: Configure a MOTD Banner

```bash
CoreSwitch(config)# banner motd "Unauthorized access is prohibited"
```

**Explanation**: Displays a message when someone connects to the device, typically used for legal warnings.

### Step 12: Save the Configuration

```bash
CoreSwitch# copy running-config startup-config
```

**Explanation**: Saves the current configuration to NVRAM so it persists after a reboot.

---

## Part 2: Implementing Basic Connectivity

### IP Configuration Table

|Device|IP Address|Subnet Mask|
|---|---|---|
|S1|192.168.1.253|255.255.255.0|
|S2|192.168.1.254|255.255.255.0|
|PC1|192.168.1.1|255.255.255.0|
|PC2|192.168.1.2|255.255.255.0|

### Steps:

1. Connect each PC to its switch using **copper straight-through** cables.
    
2. Assign IP addresses manually via PC > Desktop > IP Configuration.
    
3. Access the switch CLI and configure VLAN interface:
    

```bash
Switch> enable
Switch# configure terminal
Switch(config)# interface vlan 1
Switch(config-if)# ip address 10.10.1.1 255.255.255.0
Switch(config-if)# no shutdown
```

**Explanation**:

- `interface vlan 1`: Enters VLAN 1 interface mode (management VLAN).
    
- `ip address`: Assigns an IP address to the VLAN interface.
    
- `no shutdown`: Activates the interface.
    

4. Save configuration:
    

```bash
Switch# copy running-config startup-config
```

---

## Part 3: Cisco Router Configuration

### Step 1: Console Connection to Router (R1)

1. Connect a console cable:
    
    - PC RS232 → Router Console port
        
2. On the PC, go to **Desktop > Terminal** and press **Enter**.
    

### Step 2: Enter Privileged EXEC Mode

```bash
Router> enable
```

**Explanation**: Access advanced commands and configuration options.

### Step 3: Initial Configuration

```bash
Router# configure terminal
Router(config)# hostname R1
Router(config)# banner motd "Unauthorized access is strictly prohibited"
Router(config)# enable password Cisco
Router(config)# enable secret itsasecret
Router(config)# line console 0
Router(config-line)# password letmein
Router(config-line)# login
Router(config)# service password-encryption
Router(config)# exit
```

**Explanation**:

- `hostname R1`: Sets router hostname.
    
- `banner motd`: Sets login banner.
    
- `enable password`: Basic password for privilege mode.
    
- `enable secret`: Encrypted password (more secure).
    
- `line console 0`: Access console line config.
    
- `password letmein`: Console password.
    
- `login`: Enables console login.
    
- `service password-encryption`: Encrypts all passwords.
    
- `exit`: Return to EXEC mode.
    

### Step 4: Verify and Save Configuration

- View config:
    

```bash
R1# show running-config
```

**Explanation**: Display current configuration in memory.

- Save config:
    

```bash
R1# copy running-config startup-config
```

**Explanation**: Save configuration to NVRAM for persistence after reboot.

---

_End of Guide._