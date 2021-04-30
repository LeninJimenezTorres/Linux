## HARDWARE

```markdown
    
   Use:     `lsusb` 
   To:      show all usb peripherical component plugged to the device

```
You can use the directory of peripherical devices to find your usb or pci device driver, which is usually stored in: `/dev/`


```markdown
    
   Use:     `lspci` 
   To:      show all peripherical component interface plugged to the slots of the device.

```

```markdown
    
   Use:     `lshw` 
   To:      show all kind of devices connected to the pc.

```

```markdown
    
   Use:     `lsmod` 
   To:      show all modules loaded.
   Example:
             `lsmod | grep sound`
   Note: Wheter you need to do throubleshooting with some peripherical device, use this directory to search all your modules availables and determine possible problems with the controller of that device: 
                                    /lib/modules/`uname -r`/kernel
   
```

```markdown
    
   Use:     `modprobe` 
   To:      Load a module
   Example:
             `modprobe soundcore`
   
```

```markdown
    
   Use:     `uname` with +  `-a, -r, and others` 
   To:      Print all kind of information about the system.

```     
    
## SYSTEM

### GNU GRUB 

GRUB is a complete program for loading and managing the boot process. It is the most common bootloader for Linux distributions. A bootloader is the first software that runs when a computer starts. It loads the kernel of the operating system and then the kernel initializes the rest of the operating system: shell, display manager, desktop environment, etc.
GRUB is both a bootloader (load the OS) and a boot manager (allows you to choose between operating systems, if there is more than one on your system).

It has the directory: `/grub/`

Their configuration is stored in: 
                                    `/grub/grub.cfg` 
                                    `/etc/default/grub`
                                    `/etc/grub.d`
            
You can update grub with the command:
```markdown
                sudo update-grub
```

### Linux runlevels
                    0 system halt to shut off machine
                    1 single user (rescue) mode
                    3 multi-user mode without GUI (to server aplications, providing only terminal connections)
                    5 multi-user mode with GUI (to standar desktop machine)
                    6 reboot

To set the run level use the command:
```markdown
                    sudo telinit 0-------------> old command
                    systemctl enable multi-user.target
                    systemctl isolate rescue.target
                    
```

To see your current run level use the command:
```markdown
                    systemctl get-default
```

### Root-level directories
```markdown
                    /bin    Binary files for single user mode system commands
                    /sbin   System Binary files multi user syst3em commands
                    /boot   Linux images and boot configuration files
                    /dev    Pseudo fles representing physical and virtual devices: PCIs, usb devices.
                    /etc    Configuration files
                    /home   User files
                    /lib    Software libreries dependencies needed by binary programs
                    /root   Root user files
                    /usr    Additional binaries - non essential commands
                    /var    Updating files: logs, application data, cache  
                    /temp   Data taht only be used in the current session
```
 
### Pseudo files directories
To sudo files and commands:
```markdown
                    /proc   Files representing running system process
                    /dev    Pseudo files representing hardware devices and devices drivers
                    /sys    Data on system and kernel resources
 
```

### System commands


```markdown
                Command: locale
                Description: reflect your geographic location
                
                Command: pwd
                Description: Print working or current directory
                
                Command: env
                Description: To see all shell variables
                
                Command: locale
                Description: reflect your geographic location
                
                Command: type [command]
                Description: to search the location of the command
                
                Command: timedatectl
                         timedatectl list-timezones
                         timedatectl set-timezone [zone file]
                Description: to see time and zones
                
```




## NETWORK CONFIGURATIONS

```markdown
    
    Use: `ip addr`
    to show ip configuration

```

```markdown
    
    Use: `ip route show`
    Description: to show ip address to the router of the network
    For example:
                        default via 172.31.0.1 dev eth0 proto dhcp src 172.31.15.194 metric 100
                                    [_________]
                                         |________ my router ip address
                        
                        172.31.0.0/20 dev eth0 proto kernel scope link src 172.31.15.194
                                                                           [____________]
                                                                                  |__________ my ip address
                                                                                  
                        172.31.0.1 dev eth0 proto dhcp scope link src 172.31.15.194 metric 100
                       [__________]
                             |_________My router ip address or the default gateway

```

```markdown
    
    Use: `sudo dhclient`
    Description: It show if a dhcp server configuration is load

```

```markdown
    
    Use: `route`
    Description: To show gateway ip address configuration and loopback
    
```

```markdown
    
    Use: `ifconfig`
    Description: It's a brief abstract of the network configuration

```

```markdown
    
    Use: `netstat -i`
    Description: To show statistics of each network interface
    
    Use: `snetstat -l`
    Description: To show protocols in process and their ports

```

```markdown
    
    Use: `ss -i`
    Description: To show all news of the network interfaces

```

```markdown
    
    Use: `systemd-resolv --status`
    Description: To show the list of network configurations and their status, for instance:
                `
                Global
                    LLMNR setting: no
                    MulticastDNS setting: no
                    DNSOverTLS setting: no
                    DNSSEC setting: no
                    DNSSEC supported: no

                Link 2 (enp0s3)
                    Current Scopes: DNS            
                    DefaultRoute setting: yes            
                    LLMNR setting: yes            
                    MulticastDNS setting: no             
                    DNSOverTLS setting: no             
                    DNSSEC setting: no             
                    DNSSEC supported: no             
                    Current DNS Server: 200.107.10.105 
                    DNS Servers: 200.107.10.105 
                                 181.113.126.100
                `
                
```

### DNS

To search a ip address of a dns you can use:

```markdown
    
    Use: `host google.com`
    
    Note: this is simillar to `tracert` in windows
```

Also to search a problem with the dns you can use the `ping` command to the ip and the dns to check it.

Additionally, you can use the file or directory of the DNS configuration, which is usually stored in the directory: 
                        `cat /etc/resolv.conf`

#### Create your own DNS indices

```markdown
    
    Use: `sudo nano /etc/hosts`
    
    Here you can add your own ip/dns configuration
    
```

### SSH Connectivity 

You need install and runing a software on both the client and the server machine to enable the conection. Here I advice you the OpenSSH

```markdown
                sudo apt install openssh-server
                sudo apt install openssh-client
             
```
The ssh configuration you can find it in: `/etc/ssh`
And if you need to change the parameters you can change the file: `sudo nano ssh_config`

To connect to a ssh server you can use:
```markdown
               command: ssh pepito @ 10.0.0.1 
                            [____]   [______]
                               |         |_______ public ip address of the remote ssh system
                               |_________________ user of the remote system
```

And if you need to specify the protocol, you can use:
```markdown
               command: ssh -p 2222  pepito  @ 10.0.0.1 
                               [___] [_____]   [______]
                                 |      |          |________ public ip address of the remote ssh system
                                 |      |___________________ user of the remote system
                                 |__________________________ the specific port of the connection
```

Or if you need to run an instance of Amazon, use:
```markdown
               command: ssh -i /home/mortem/Documents/key.pem  ubuntu @ 10.0.0.1 
                               [_____________________________] [_____]  [_______]
                                              |                   |         |________ public ip address of remote instance
                                              |                   |__________________ user of the remote system          
                                              |______________________________________ This is the key generated in AWS when you create the instance, you need download it.
                                              
```

### SCP - Secure Copy

To make secure copy files between remote machines. You can use:
```markdown
                command: scp /home/mortem/Documents/pepito.text  ubuntu @ 10.0.1.12  : /home/remote_user/Documents/
                             [________________________________]  [____]   [________]   [__________________________]
                                             |                      |          |                    |________________ location or directory to place the shared file into remote user
                                             |                      |          |_____________________________________ public ip address of remote system
                                             |                      |________________________________________________ remote user 
                                             |_______________________________________________________________________ local document or file that you want to share to the remote user
                             
```


## SYSTEM NAVEGATION

### Directories
```markdown
    
    Use `.` to refer to the current directory
    
    Use `..` to refer to the above directory
  
```

### To get a specific column of a .csv
```markdown
    
            `cut -d: -f3 archivo.csv`
                  [_] [_] 
                   |   |_ _ The number of column that we need to get the value  
                   |
                    - The delimiter of the columns
  
```

### To sort information
```markdown

            You can use:
                            `sort`: to sort in descendent way
                            `sort -r`: to sort in ascendent way
                            `sort -n`: to sort according to the value of the column

```

### To count characters in a file
```markdown

            `wc file.txt`
            `--wordcount file.txt`

```

## USERS AND GROUPS PERMISSIONS


## SCRIPTING

### Shell scripting
You can use any shell that you prefer, the only you need is to install that shell or be sure that it's already installed. To do this you can search all of you shells in the directory: `/etc/shells`

The most used is bash shell, so you can install right now.

### Shebang / Hashbang
This is the usually name given to the bash call in a script, by the command line:

```markdown
                    #! /bin/bash
```

### Variable declare
```markdown
                declare  -i  variable1
                         [_] [_______]
                          |      |_______ name of variable
                          |______________ type of variable, integer int his case
```

### Export a variable
```makdown
                export variablename
```

### Loops - For command
```markdown
                for  s  in  $array
                    [_]     [____]
                     |         |______ the list of iterations
                     |________________ the variable of iterations
                     
                     do [action]
                     done
                     
           For instance:
                for i in {0..10..2} -----------------------------> It will begin in 0 up to 10 with increments of 2.
                    do echo "We have been through this $i times already!"
                    done
```

### If condition
```markdown
                if test [condition]
                   [__] [_________]
                     |       |____________ you can use logical operator like: `A != B`. Notice that here you need to separate each term with a space.
                     |____________________ you can replace it with brackets to revolve the condition, like: `if [ $A != $B ]`. (You need to use a space after each term!!!) 
                     
                            then [action]
                    
                    elif 
                    
                            then [action]
                    
                    else
                
                fi
```

### Switch condition
```markdown
                    while
```

### While loop
```markdown
                    while
```




# Autor:
Lenin Jiménez Torres

### Support or Contact
[LinkedIn](https://www.linkedin.com/in/lenin-jim%C3%A9nez-ba9251134/)
