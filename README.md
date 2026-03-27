# EXPT.NO-2-IMPLEMENTATION-OF-DISTANCE-VECTOR-ROUTING-PROTOCOL-RIP

# AIM:
To connect computers in multiple networks using Distance Vector Routing Protocol and to verify the connectivity between computers.

# EQUIPMENTS REQUIRED:
<img width="1014" height="262" alt="Screenshot 2026-03-25 195945" src="https://github.com/user-attachments/assets/38d58481-98e6-43d3-b7b4-17f38eb60cf9" />




# IP ASSIGNMENT:
<img width="1002" height="468" alt="Screenshot 2026-03-25 200006" src="https://github.com/user-attachments/assets/bae70baf-9293-4591-9e0b-db2601712c6a" />



# NETWORK DIAGRAM:
<img width="952" height="418" alt="Screenshot 2026-03-25 200030" src="https://github.com/user-attachments/assets/dad82430-ae06-47d0-b42e-8a12e8eefb60" />

# PROCEDURE:
<img width="576" height="365" alt="image" src="https://github.com/user-attachments/assets/f4245c26-a2f8-4621-b317-0a2c8049f764" />
 
# PROGRAM

Router0 Program
```
Click Router 0 and in CLI TYPE THIS 
Router> enable
Router# configure terminal 
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0 
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0 
Router(config-if)# no shutdown
Router(config-if)# exit 
Router(config)# router rip 
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0 
Router(config-router)# exit
```

Router1 Program
```
Click Router 1 and in CLI TYPE THIS 
Router> enable
Router# configure terminal 
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0 
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.4.1 255.255.255.0 
Router(config-if)# no shutdown
Router(config-if)# exit 
Router(config)# router rip 
Router(config-router)# version 2
Router(config-router)# network 192.168.3.0
Router(config-router)# network 192.168.4.0 
Router(config-router)# exit
```

Steps to Check the Output:

**1. Verify RIP Routing Table on Routers**

To check if RIP is working and the routes are learned from the other router, you need to inspect the routing table on each router. Click Router 0 In the CLI window, type:

**Router# show ip route**

You should see routes for the networks connected to Router1 (192.168.3.0 and 192.168.4.0) via RIP. The output might look something like this:

R 192.168.3.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1 

R 192.168.4.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1

For Router1, enter the same command:

**Router# show ip route**

You should see routes for the networks connected to Router0 (192.168.1.0 and 192.168.2.0) via RIP:

R 192.168.1.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0 

R 192.168.2.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0

**2. Ping from PC to PC**

You can also check connectivity between the PCs on different networks to ensure that RIP is correctly routing packets across the routers.

Example: Ping from PC0 (192.168.1.2) to PC3 (192.168.3.2):

Click on PC0, go to the Desktop tab.

Open the Command Prompt.

Use the ping command:

ping 192.168.3.2

If everything is configured correctly, you should receive replies from PC3.

Similarly, you can ping between other PCs (e.g., from PC2 to PC5) to verify network connectivity.

# OUTPUT
## Router 0 Output
<img width="933" height="918" alt="Screenshot 2026-03-25 201115" src="https://github.com/user-attachments/assets/f6d9cbc7-5b96-4dca-aca6-697cf07fb9fe" />

## Router 1 Output
<img width="928" height="911" alt="Screenshot 2026-03-25 201139" src="https://github.com/user-attachments/assets/382d59cd-62f9-4af0-b513-543d30d06cc7" />



# RESULT:

Thus the computers in multiple networks using Distance Vector Routing 
