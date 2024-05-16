# 4. EXECUTION OF NETWORK COMMANDS
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program:

PING COMMAND:

CLIENT:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output
PING COMMAND:
CLIENT:
![318811465-2f1a61c8-198c-4698-86f4-18dd523d201e](https://github.com/Harsetha/4.Execution_of_NetworkCommends/assets/149985878/cf4c5797-85cb-4587-8980-9863888de906)



SERVER:
![318811620-ee38335b-f844-4f1a-94fd-aec00c83371b](https://github.com/Harsetha/4.Execution_of_NetworkCommends/assets/149985878/e87682b9-8527-4e5a-aed3-299360fc54e9)


TRACEROUTE COMMAND:

![318811837-291348a5-2130-4e90-a85b-19516c4cf3f6](https://github.com/Harsetha/4.Execution_of_NetworkCommends/assets/149985878/46d5795b-776a-4837-a7f4-e49976f0df8d)

## Result
Thus Execution of Network commands Performed 
