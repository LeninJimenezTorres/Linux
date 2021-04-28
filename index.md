## HARDWARE

```markdown
    
   Use:     `lsusb` 
   To:      show all usb peripherical component plugged to the device

```

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


## Directories
```markdown
    
    Use `.` to refer to the current directory
    
    Use `..` to refer to the above directory
  
```

## To get a specific column of a .csv
```markdown
    
            `cut -d: -f3 archivo.csv`
                  [_] [_] 
                   |   |_ _ The number of column that we need to get the value  
                   |
                    - The delimiter of the columns
  
```

## To sort information
```markdown

            You can use:
                            `sort`: to sort in descendent way
                            `sort -r`: to sort in ascendent way
                            `sort -n`: to sort according to the value of the column

```

## To count characters in a file
```markdown

            `wc file.txt`
            `--wordcount file.txt`

```

## 
