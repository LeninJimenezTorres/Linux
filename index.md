## HARDWARD 

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
   Note: Use the modules directory to search all your modules: /lib/modules/`uname -r`/kernel
   
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
