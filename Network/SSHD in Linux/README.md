# "SSHD" in Linux

## Description

In Linux, sshd refers to the SSH daemon, which is a background process responsible for handling incoming Secure Shell (SSH) connections. SSH is a cryptographic network protocol used for secure communication over an unsecured network. The SSH protocol provides encrypted communication between two hosts, enabling secure remote access and file transfer.

1. **Functionality**:
- sshd is the server component of the SSH protocol suite. It listens for incoming SSH client connections on TCP port 22 (by default) and facilitates secure remote access to the system.
- When a remote user attempts to connect to a Linux system via SSH, sshd authenticates the user's credentials (usually username and password or SSH keys) and grants access if authentication is successful.
- Once authenticated, sshd provides an interactive shell session or executes the requested command on behalf of the user, all while encrypting the communication to ensure confidentiality and integrity.

2. **Configuring SSH**:
- The main configuration file for sshd is typically located at **`/etc/ssh/sshd_config`**. You can edit this file using a text editor such as nano or vi. Here are some common configuration options:
	- **Port**: Specifies the port on which sshd listens for incoming connections (default is 22).
	- **PermitRootLogin**: Determines whether root login is allowed (set to no for better security).
	- **PasswordAuthentication**: Specifies whether password authentication is allowed (consider using public key authentication instead).
	- **PubkeyAuthentication**: Controls whether public key authentication is allowed.
	- **AllowUsers**: Specifies which users are allowed to connect via SSH.
	- **DenyUsers**: Specifies which users are not allowed to connect via SSH.
- After making changes to the sshd_config file, you need to restart the SSH service for the changes to take effect (sudo systemctl restart sshd).

3. **Security Features**:
- sshd implements various security features to protect against unauthorized access and mitigate common security threats. These include:
	- Encryption of communication using strong cryptographic algorithms (e.g., AES, RSA).
	- Support for public key authentication, which is more secure than password-based authentication.
	- Protection against brute-force attacks through configuration options like MaxAuthTries and LoginGraceTime.
	- Use of privilege separation to limit the impact of potential vulnerabilities in the SSH daemon.

4. **Logging and Monitoring**:
- sshd logs information about SSH connections, authentication attempts, and other relevant events to the system log files (e.g., **`/var/log/auth.log`** on **`Debian-based systems`**).
- Administrators can monitor SSH activity, audit log files, and use intrusion detection systems to detect suspicious behavior or unauthorized access attempts.

5. **Management**:
- sshd can be managed using various system administration tools, such as systemd (system and service manager), which provides commands for starting, stopping, restarting, and reloading the SSH daemon (**`systemctl start|stop|restart|reload sshd`**).
- Administrators can also manage SSH-related settings and access controls using tools like sshd_config, sshd-keygen, and sshd-checkconf.

6. **Essential Commands** :
```
sudo systemctl start sshd    				 # To Start SSH Service
sudo systemctl stop sshd      			 # To Stop SSH Service
sudo systemctl restart sshd       	 # To Restart SSH Service
sudo systemctl reload sshd       		 # To Reload SSH Service
ssh <username>@<hostname_or_IP>      # Check SSH Status
```
