# 4.Execution_of_NetworkCommands
## Name: Vinuthaa NN
## Reg no: 212224040362

## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
### To do this EXPERIMENT- follows these steps:

1. In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
2. All commands related to Network configuration which includes how to switch to privilege mode and normal mode and how to configure router interface and how to save this configuration to flash memory or permanent memory.

  This commands includes

    • Configuring the Router commands
    • General Commands to configure network
    • Privileged Mode commands of a router 
    • Router Processes & Statistics
    • IP Commands
    • Other IP Commands e.g. show ip route etc.

## Program
### Client
```.py
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except Exception as e:  # Catch all errors
        c.send(f"Error: {str(e)}".encode())
```

### Server
```.py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```


## Output
<img width="1691" height="920" alt="image" src="https://github.com/user-attachments/assets/34aef1bf-31a7-4c7d-9c0d-392fa621581b" />

## Result
Thus Execution of Network commands Performed 
