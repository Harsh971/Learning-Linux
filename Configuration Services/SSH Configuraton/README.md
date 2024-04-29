# SSH Configuration in Linux

## Introduction :
Configuring **SSH (Secure Shell)** client and server in Linux involves setting up SSH connections for secure remote access and file transfer between systems. SSH provides encrypted communication channels over unsecured networks, ensuring confidentiality and integrity of data transmitted between client and server.

### Configuring SSH Server::
1. **Installation:**
Ensure that the SSH server package (openssh-server) is installed on the server:
```
sudo  apt-get  update
sudo  apt-get  install  openssh-server
```
2. **Configuration:**
The SSH server configuration file is located at /etc/ssh/sshd_config. Edit this file to configure SSH server settings
```
sudo nano /etc/ssh/sshd_config
```
The SSH server configuration file (sshd_config) contains various settings that govern the behavior of the SSH server. Here's a breakdown of some key configuration options and common changes you might make:
  - **Port**: By default, SSH operates on port 22. You might consider changing this port for security reasons to a non-standard port to make it harder for attackers to find and exploit your SSH server. 
  ```
    Port 2222
  ```
  - **PermitRootLogin**: Determines whether root login via SSH is allowed. It's generally recommended to disable root login and use a regular user account with sudo privileges instead. 
  ```
    PermitRootLogin no
  ```
  - **PasswordAuthentication**: Controls whether password-based authentication is allowed. For enhanced security, it's advisable to disable password authentication and use public key authentication instead.
  ```
    PasswordAuthentication no
  ```
  - **PubkeyAuthentication**: Specifies whether public key authentication is allowed. Public key authentication is generally more secure than password authentication. Ensure this option is enabled if you intend to use public key authentication.
  ```
    PubkeyAuthentication yes
  ```
  - **AllowUsers**: Restricts SSH access to specific users. This option allows you to specify which users are allowed to connect via SSH.
  ```
    AllowUsers username1 username2
  ```

<br>

3. **Restart SSH Service:**
After making changes to the configuration file, restart the SSH service for the changes to take effect
```
sudo systemctl restart ssh
```

<br>

4. **Firewall Configuration:**
If a firewall is enabled, ensure that it allows SSH traffic on the configured port (default is 22)
```
sudo ufw allow OpenSSH
```

<hr>

### Configuring SSH Client:
1.  **Installation:**
SSH client software is usually pre-installed on most Linux distributions. If not, you can install it using:
```
sudo apt-get install openssh-client
```
2. **Configuration:**
The SSH client configuration file is located at **`~/.ssh/config`** (per-user configuration) or **`/etc/ssh/ssh_config`** (system-wide configuration). You can customize SSH client behavior by editing this file.

3. **Generating SSH Key Pair (Optional):**
To use public key authentication, generate an SSH key pair on the client machine
```
ssh-keygen -t rsa -b 2048
```
This command generates a 2048-bit RSA key pair. Follow the prompts to specify the file location and passphrase.

4. **Connecting to SSH Server:**
To connect to an SSH server, use the ssh command followed by the server's hostname or IP address
```
ssh username@hostname
```
Replace username with the username on the server and hostname with the hostname or IP address of the server.
