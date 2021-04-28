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
