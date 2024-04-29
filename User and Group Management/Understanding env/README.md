# env File in Linux

## Introduction :
In Linux, an environment file, often referred to as an "env file," is a text file containing environment variables. Environment variables are dynamic named values that affect the behavior of processes running within an operating system or shell session. They are used to customize the behavior of software applications, define system-wide settings, and provide configuration parameters.

An environment file typically consists of key-value pairs, where each line represents a single environment variable assignment in the format KEY=VALUE. The key represents the name of the environment variable, and the value represents its corresponding value.

Environment files are commonly used in Linux-based systems for configuring applications, services, and system-wide settings. They provide a convenient way to manage and organize environment variables, especially when dealing with complex configurations or multiple settings.

### Some common use cases for environment files include:

- **Configuration Management:** Environment files are used to store configuration parameters for applications and services, allowing administrators to customize their behavior without modifying the application code.
- **Docker and Containers:** In containerized environments, environment files (often named .env files) are used to pass configuration parameters to Docker containers, defining environment variables that influence container behavior.
- **Shell Sessions:** Environment files can be sourced within shell scripts or interactive shell sessions to set environment variables for the duration of the session. This allows users to customize their shell environment with specific settings or preferences.
- **System Startup:** Some Linux distributions use environment files to define system-wide environment variables during the boot process. These variables may influence system behavior or provide configuration options for system services.

### Example 1 : 
To access the env file we can run the following Command :
```
printenv     OR       env
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/Understanding%20env/image1.png">

### Example 2 : 
As we saw that all entries in env file are **KEY=VALUE** pairs, so lets understand its working
As seen in above image, all **KEY** are **`Capatilized`** and all **Values** are **`Lowercased`** . Therefore all **KEY** can be used as Global Variables
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/User%20and%20Group%20Management/Understanding%20env/image2.png">

which also means 
```
touch $HOME/test.txt  
equals
touch /home/harsh/test.txt
```
### Example 3 :
All env Variables are stored in "/etc/environments" wherein we can add our custom env variables
```
sudo  vim  /etc/environments    #   to open vim terminal
NAME = Harsh                    #   added some variables
:wq!                            # save changes in vim terminal

echo $NAME                      #    Harsh
```
