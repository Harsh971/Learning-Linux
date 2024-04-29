# email Aliases in Linux

## Introduction :

In Linux, email aliases are used to redirect email messages sent to one email address to another email address or multiple email addresses. Email aliases are commonly used for various purposes, such as simplifying email addresses, distributing messages to multiple recipients, and managing email routing within an organization.

## Purpose of Email Aliases:
- **Simplifying Email Addresses**: Email aliases allow users to create alternative email addresses that are easier to remember or type than their primary email addresses.
- **Managing Email Routing**: Email aliases can be used to route messages to specific recipients or groups based on predefined rules or criteria.
- **Distributing Messages**: Email aliases enable messages to be distributed to multiple recipients simultaneously without the need to specify each recipient individually.

## Alias Types:
- **User-Level Aliases**: User-level aliases are defined and managed by individual users. They typically apply to a single user's mailbox and allow the user to define additional email addresses that redirect to their primary email address.
- **System-Level Aliases**: System-level aliases are defined and managed at the system level by administrators. They apply to all users on the system and allow administrators to define global email aliases for routing messages to specific users or groups.

## Configuration Files:
- User-Level Aliases: User-level aliases are typically configured in a file called **`.forward`** located in the user's home directory. This file contains a list of email addresses or mailbox paths to which messages should be forwarded.
- System-Level Aliases: System-level aliases are configured in a system-wide aliases file, commonly **`/etc/aliases`** or **`/etc/mail/aliases`**. This file contains a list of alias definitions mapping alias names to email addresses or mailbox paths.

## Important Commands and Steps

### 1. Creating a simple Mail Server (postfix)
```
sudo  dnf  install  postfix
```
- **`dnf`**: The Dandified YUM (DNF) package manager, used on Fedora-based Linux distributions, including Fedora, CentOS, and RHEL.
- **`install postfix`**: Instructs dnf to install the postfix mail transfer agent (MTA) package. Postfix is a popular MTA used for routing and delivering email messages on Linux systems.

### 2. Start and Enable Mail Server (postfix)
```
sudo  systemctl  start  postfix
sudo  systemctl  enable  postfix
```
- **`systemctl`**: The systemctl command is used to control systemd services on Linux systems.
- **`start postfix`**: Instructs systemctl to start the postfix service, which launches the Postfix mail server and enables it to process incoming and outgoing email messages.
- **`enable postfix`**: Instructs systemctl to enable the postfix service to start automatically at system boot.

### 3. Sending a test mail and verify process
```
sendmail  username@localhost  <<<  "Hello This is a test mail"
cat  /var/spool/mail/username
```
- **`/var/spool/mail/`**: The system mail spool directory, where incoming email messages are stored temporarily until they are delivered to user mailboxes.
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/Configuration%20Services/Email%20Aliases/image1.png">

### 4. Make Changes in Aliaces File (/etc/aliases)
```
sudo  vim  /etc/aliases
```
- **`/etc/aliases`**: The system-wide aliases configuration file, where email aliases are defined. It is used to map alias names to email addresses or mailbox paths.
- Here we add a KEY=VALUE pair which defines a new Aliase

### 5. Save the changes to Aliases Database
```
sudo  newaliases
```
- **`newaliases`**: A command-line utility used to rebuild the Postfix aliases database after modifying the /etc/aliases file.
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/Configuration%20Services/Email%20Aliases/image1.png">