# User Accounts in Linux

## Introduction :
Managing users in Linux involves creating, modifying, and deleting user accounts, as well as managing user permissions and access rights. Here's an overview of common tasks and commands for managing users in Linux:

## Tasks :
**1. Creating Users :**
```
sudo  useradd  username
```
By default, this command only creates the user account. You may need to set a password for the user using the passwd command:
```
sudo  passwd  username
```
- With this in the System, a new User name "username" is created. Also a new UserGroup named "username" is created holding only this particular User into it
- A Directory named "/home/username" is created where all user files are stored
- Default shell "/bin/bash" will be allocated to this user

**2. Deleting User :**
```
sudo  userdel  username
```
- This Command will delete the User name "username" and its UserGroup named "username".
- However, the directory "/home/username" which holds user files is not removed by Default. 
- To remove this aswell we can execute
```
sudo  userdel  --remove  username
OR
sudo  userdel  -r  username
```

**3. Change Default Shell :**
- The default shell "/bin/bash" is allocated to every new user, to modify this
```
sudo  useradd  --shell  /bin/othershell  username
OR
sudo  useradd  -s  /bin/othershell  username
```

**4. View all User Information :**
All users informations are stored in "/etc/passwd" location
```
cat  /etc/passwd
username : x : userid : primary-groupid :: home-directory : login-shell
```

**5. Assign a specific UserID :**
```
sudo  useradd  --uid  1100  username
```
- This creates a new user named "username" with uid as 1100

**6. Get information about current User :**
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/User%20Accounts/image1.png">

**7. System Users :**
- Default UserID for the Default User is 1000
- UserID's of new Users are < 1000
- UserID's of new System Users are > 1000
```
sudo  useradd  --system  username
```

**8. Modify User Informations :**
- Modify Home Directory of an existing User
```
sudo  usermod  --home  /home/otherdir  --move-home  username
OR
sudo  usermod  -d  /home/otherdir  -m  username
```
- Modify User Name of an existing User
```
sudo  usermod  --login  newname  prevname
OR
sudo  usermod  -l  newname  prevname
```
- Modify User Login Shell of an existing User
```
sudo  usermod  --shell  /bin/othershell  username
OR
sudo  usermod  -s  /bin/othershell  username
```
- Lock User Account
```
sudo  usermod  --lock  username
OR
sudo  usermod  -L  username
```
- Unlock User Account
```
sudo  usermod  --unlock  username
OR
sudo  usermod  -U  username
```
- Set Expiration Date of a User Account
```
sudo  usermod  --expiredate  YYYY-MM-DD  username
OR
sudo  usermod  -e  YYYY-MM-DD  username
```
Account Expiration Completely DISABLES User Login
- Set Expiration Date of a User Account Password
```
sudo  chage  --lastday  DD  username
OR
sudo  usermod  -d  DD  username
```
User needs to change Password After DD Days
