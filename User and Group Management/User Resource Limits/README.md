# User Resource Limits in Linux

## Introduction :
In Linux, user resource limits, also known as ulimits (User Limits), define the maximum amount of system resources that a user or process can consume. These limits are set to prevent individual users or processes from monopolizing system resources, causing performance degradation, or potentially crashing the system due to resource exhaustion.

User resource limits can be set and managed using the ulimit command or by configuring system-wide settings in the **`/etc/security/limits.conf`** file. Here's an overview of the key resource limits that can be set for users:

- **Maximum CPU Time:** Defines the maximum amount of CPU time (in seconds) that a user or process can consume. This limit prevents CPU-bound processes from monopolizing CPU resources and causing performance issues for other users or processes.
- **Maximum Memory Usage:** Specifies the maximum amount of memory (in kilobytes) that a user or process can allocate. This limit prevents memory-intensive processes from consuming excessive system memory, leading to out-of-memory errors or system instability.
- **Maximum Open Files:** Sets the maximum number of files that a user or process can have open simultaneously. This limit prevents file descriptor exhaustion and ensures that the system can handle a reasonable number of open files without running out of resources.
- **Maximum Number of Processes:** Defines the maximum number of processes that a user can have running simultaneously. This limit prevents users from spawning an excessive number of processes, which can degrade system performance and lead to resource contention.
- **Maximum File Size:** Specifies the maximum size (in kilobytes) of individual files that a user can create. This limit prevents users from creating excessively large files that could consume a disproportionate amount of disk space or exceed filesystem limitations.
- **Maximum Number of Threads:** Sets the maximum number of threads that a user or process can create. This limit prevents multi-threaded applications from spawning an excessive number of threads, which can lead to increased memory usage and scheduling overhead.
- **Maximum File Locks:** Defines the maximum number of file locks that a user or process can acquire simultaneously. This limit prevents users from monopolizing file locks, which can lead to resource contention and deadlock situations.

Setting appropriate user resource limits is essential for maintaining system stability, preventing resource exhaustion, and ensuring fair resource allocation among users and processes. By enforcing resource limits, administrators can mitigate the risk of system instability, improve system performance, and enhance overall system reliability.

## limits.conf File
All the User Resource Limits as stored in the **`/etc/security/limits.conf`** File
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/User%20Resource%20Limits/image1.png">

## Domain
Domain includes basically 3 types of Users to target : 
- **Username** : Denoted directly by their name
- **GroupName** :  Denoted by "@" before groupname
- **All Users** : Denoted by "*"

## Limit Types
- **Hard Limit** : A Hard Limit cannot be overwritten by a regular User
- **Soft Limit** :  A Soft Limit states the default limit of resources allocated to user and as per need in future it can be increased by only MAX till Hard Limit
- **-** : - defines as a static value for resources which cant be increased nor decreased
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/User%20Resource%20Limits/image2.png">
As per the above example we can see the error when more than allocated resources are demanded to use