# Network Manager.service in Linux

## Description

In Linux, Network Manager is a service responsible for managing network connections. It's a daemon (a background process) that handles various network-related tasks such as connecting to different types of networks (like wired, wireless, VPNs), configuring network interfaces, and managing network settings.

Here's a breakdown of what Network Manager.service does:

- ***Connection Management*** : Network Manager handles the connection to different networks, whether they are wired, wireless, or VPN connections. It can automatically detect available networks and connect to them based on predefined configurations or user input.
- ***Network Interface Configuration***: It manages the configuration of network interfaces. This includes setting IP addresses, subnet masks, gateways, DNS servers, and other parameters necessary for network communication.
- ***Network Profile Management***: Network Manager allows users to create and manage network profiles. These profiles contain configurations for specific networks, such as SSID and security settings for wireless networks, or IP configurations for wired networks.
- ***Network Security***: It provides features for securing network connections, such as support for various encryption protocols like WPA/WPA2 for wireless networks and VPN protocols for secure remote access.
- ***Network Troubleshooting***: Network Manager includes tools for diagnosing and troubleshooting network issues. It can log network events, display connection status, and provide information about network interfaces and their configurations.

The **`".service"`** extension in "Network Manager.service" indicates that it's a systemd service unit file. Systemd is a system and service manager for Linux operating systems, and it uses unit files with the **`".service"`** extension to define services and their configurations. The Network Manager service unit file specifies how the Network Manager daemon should be started, stopped, and managed by the system.
<hr>

Certainly! nmcli is a powerful command-line tool for managing Network Manager on Linux systems. It allows users to interact with Network Manager and perform various network-related tasks directly from the command line. 

1. ***Viewing Network Connections***:
- ***```nmcli connection show ```***: This command lists all available network connections along with their details such as connection name, UUID, device, and connection type.
- ***```nmcli connection show --active```*** : Shows only active connections.

2. ***Managing Network Connections***:
- ***```nmcli connection up <connection-name>```*** : Brings up a specific network connection by its name.
- ***```nmcli connection down <connection-name>```*** : Takes down a specific network connection by its name.
- ***```nmcli connection delete <connection-name>```*** : Deletes a network connection profile by its name.

3. ***Viewing Network Devices***:
- ***```nmcli device show```*** : Displays information about all available network devices including their type, state, MAC address, and IP addresses.
- ***```nmcli device status```*** : Shows the status of network devices including their connection status and whether they are active or not.

4. ***Managing Wi-Fi Networks***:
- ***```nmcli device wifi list```*** : Lists available Wi-Fi networks along with their signal strength, security type, and other details.
- ***```nmcli device wifi connect <SSID> password <password>```*** : Connects to a specific Wi-Fi network by specifying its SSID and password.

5. ***Viewing Connection Details***:
- ***```nmcli connection show <connection-name>```*** : Shows detailed information about a specific network connection including its settings and configurations.

6. ***Modifying Connection Properties***:
- ***```nmcli connection modify <connection-name> <property> <value>```*** : Modifies properties of a network connection. For example, you can change the IP address, gateway, DNS server, etc.

7. ***Managing VPN Connections***:
- ***```nmcli connection show --active```*** : Lists active VPN connections.
- ***```nmcli connection up <vpn-connection-name>```***: Connects to a specific VPN connection.
- ***```nmcli connection down <vpn-connection-name>```***: Disconnects from a specific VPN connection.

8. ***Network Troubleshooting***:
- ***```nmcli general status```***: Shows the overall status of Network Manager, including the connectivity state and the number of active connections.
