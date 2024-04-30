# "ss" and "netstat" Utilities in Linux

## Description

Both ***`ss`*** and ***`netstat`*** are command-line utilities used for displaying information about network connections, routing tables, and network interfaces on Linux systems. They provide similar functionality, but ss is considered more powerful and efficient compared to netstat, especially for retrieving socket statistics.

## 1. ss Utility
The  ***`ss`*** command is a powerful utility in Linux used for displaying detailed socket statistics, including information about network connections, routing tables, and network interfaces. The name  ***`ss`*** stands for ***`socket statistics`***.

Here's a detailed explanation of ss and its common usage:

1. **Functionality**:
- ss is primarily used to retrieve socket statistics, including TCP, UDP, and UNIX sockets.
- It provides information about active connections, listening sockets, and other socket-related details.
- ss can display information about network interfaces, routing tables, and multicast group memberships.

2. **Common Usage**:
- **`ss -t`** : Displays TCP sockets.
- **`ss -u`** : Displays UDP sockets.
- **`ss -l`** : Shows listening sockets.
- **`ss -a`** : Shows all sockets (both listening and non-listening).
- **`ss -n`** : Displays numerical addresses and port numbers instead of resolving them to hostnames and service names.
- **`ss -p`** : Shows the process using each socket (requires root privileges).
- **`ss -i`** : Displays information about network interfaces.
- **`ss -r`** : Shows the routing table.
- **`ss -m`** : Displays multicast group memberships.
- **`ss -h or ss --help`** : Shows the help message with a list of available options.

3. **Advantages**:
- ss is more efficient and faster than its predecessor netstat because it directly reads socket information from the kernel, avoiding the need to parse data from /proc.
- It provides more detailed socket information and supports advanced filtering options, making it a powerful tool for network diagnostics and troubleshooting.

4. **Notes**:
- The output of ss provides detailed information about each socket, including the protocol (TCP/UDP), state of the connection, local and remote addresses, and port numbers.
- For listening sockets, it shows the listening address and port number along with the process ID (if available).
- ss also provides various additional information depending on the options used, such as routing information, interface statistics, and multicast group memberships.
- ss requires root privileges to display information about processes using sockets (-p option).
- It is included in the iproute2 package and is available on most Linux distributions.
- While ss may have a steeper learning curve compared to netstat, it is considered a more modern and powerful tool for managing sockets and network connections in Linux.
<hr>

## 2. netstat Utility

The netstat command is a versatile and widely-used utility in Linux for displaying network-related information. It provides details about network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.

1. **Functionality**:
- netstat stands for "network statistics" and is used to query the networking subsystem in the Linux kernel to retrieve various network-related statistics.
- It can display information about active network connections, listening sockets, routing tables, and interface statistics.
- netstat is helpful for diagnosing network-related issues, monitoring network activity, and analyzing network configuration.

2. **Common Usage**:
- **`netstat -tuln`** : Lists all TCP and UDP listening ports along with their numeric addresses and port numbers.
- **`netstat -rn`** : Displays the kernel routing table, showing information about the network routes.
- **`netstat -a`** : Shows all active connections and listening sockets, including both TCP and UDP.
- **`netstat -s`** : Displays a summary of network statistics, including packet and byte counts for various protocols.
- **`netstat -i`** : Shows statistics for network interfaces, including packet and error counts.
- **`netstat -r`** : Shows the kernel routing table, similar to netstat -rn.
- **`netstat -p`** : Displays the process ID (PID) and program name associated with each socket (requires root privileges).
- **`netstat -c`** : Continuously updates the display at regular intervals, providing real-time network monitoring.

3. **Advantages**:
- netstat is a widely-used and familiar tool for network monitoring and diagnostics in Linux.
- It provides a quick overview of network connections, routing tables, and interface statistics, making it useful for various network-related tasks.

4. **Notes**:
- The output of netstat includes information such as local and remote addresses, protocol (TCP/UDP), state of the connection, and process ID (if available).
- For listening sockets, it shows the local address and port number along with the process name and PID (if available).
- netstat also provides various network statistics, such as packet and byte counts, error statistics, and interface statistics.
- Some options of netstat, such as -p (show process ID) and -i (show interface statistics), require root privileges to display additional information.
- While netstat is still commonly used, it has been deprecated in favor of newer tools such as ss (Socket Statistics), which provide more detailed information and better performance.
