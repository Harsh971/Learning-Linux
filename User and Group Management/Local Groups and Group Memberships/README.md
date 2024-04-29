# User Groups in Linux

## Introduction :
Understanding user groups and setting individual permissions is essential for effective access control, security management, and resource sharing in Linux environments. By leveraging user groups and assigning appropriate permissions, administrators can enforce security policies, streamline administrative tasks, and ensure efficient resource management across the organization.

- **Granular Access Control:** User groups allow administrators to assign permissions and access rights to multiple users simultaneously. By organizing users into groups based on their roles, departments, or access requirements, administrators can apply consistent permissions across multiple users, simplifying access management and ensuring granular control over who can access what resources.
- **Simplified Administration:** Grouping users with similar permissions streamlines administrative tasks such as user management and access control. Instead of assigning permissions to individual users one by one, administrators can simply assign permissions to the group, reducing the administrative overhead and ensuring consistency in access policies.
- **Security:** User groups play a crucial role in enforcing the principle of least privilege, which states that users should only be granted the minimum level of access necessary to perform their tasks. By grouping users based on their job roles or access requirements, administrators can assign appropriate permissions to each group, minimizing the risk of unauthorized access, data breaches, or malicious activities.
- **Efficient Resource Management:** Grouping users with similar permissions allows for efficient resource management and resource sharing. For example, users belonging to the same group can share files, directories, or other resources without needing to individually set permissions for each user. This simplifies resource sharing and collaboration among users, enhancing productivity and efficiency.
- **Scalability:** Group-based access control scales more efficiently as the number of users and resources grows. Instead of managing permissions for each user individually, administrators can simply assign or modify permissions for the group, making it easier to maintain access control policies in large-scale environments.

### Case 1 : 
In an organization , there are several Files which are to be accessed only be those Users that are Developers, so here we can Create a Group named "Developers" and Assign required Access Permissions for that Files to that Group which results to only allow access to those Files who are a part of Developer Group
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/Local%20Groups%20and%20Group%20Memberships/image1.png">

### Case 2 : 
One Particular User can be a part of Multiple Groups at any instance
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/Local%20Groups%20and%20Group%20Memberships/image2.png">
When a User is added, it is assigned its **Primary / Login Group** 

## Tasks :
**1. Create New Groups :**
```
sudo  groupadd  groupname
```
**2. Adding User to a Group :**
``` 
sudo  gpasswd  --add  username  groupname
OR
sudo  gpasswd  -a  username  groupname
```
**3. View All Groups, a User belongs to  :**
```
groups  username
```
**4. Remove User from a Group :**
``` 
sudo  gpasswd  --delete  username  groupname
OR
sudo  gpasswd  -d  username  groupname
```
**5. Change the Primary User Group  :**
```
sudo  usermod  -g  groupname  username
OR
sudo  usermod  --gid  groupname  username
```
**6. Change Group Name:**
```
sudo  usermod  --new-name  newgrpname  prevgroupname
OR
sudo  usermod  -n  newgrpname  prevgroupname
```
**7. Delete a Group :**
```
sudo  groupdel  groupname
```
**NOTE :** We cannot delete Primary Group


## Refer the Following for File Permissions :
<a href="https://github.com/Harsh971/Learning-Linux/tree/main/General/File%20Permissions">**`File Permissions in Linux`**</a>