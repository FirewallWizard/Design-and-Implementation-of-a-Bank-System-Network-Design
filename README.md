# Design-and-Implementation-of-a-Bank-System-Network-Design

## Objective
TD is a Canadian company that deals with Banking and Insurance. The company intends to expand its service across Asia, having the first branch in Mumbai, India. The company has secured a four-story building to operate in Mumbai.

# Office Layout and Equipment Distribution

## First Floor

| Department      | No. of PC | No. of Printers |
|-----------------|-----------|-----------------|
| Management      | 20        | 4               |
| Research        | 20        | 4               |
| Human Resource  | 20        | 4               |

## Second Floor

| Department      | No. of PC | No. of Printers |
|-----------------|-----------|-----------------|
| Marketing       | 20        | 4               |
| Accounting      | 20        | 4               |
| Finance         | 20        | 4               |

## Third Floor

| Department           | No. of PC | No. of Printers |
|----------------------|-----------|-----------------|
| Logistics and Store  | 20        | 4               |
| Customer Care        | 20        | 4               |
| Guest Area           | 20        | 2               |

## Fourth Floor

| Department     | No. of PC    | No. of Printers | Services                    |
|----------------|--------------|-----------------|----------------------------|
| Administrations| 20           | 2               |                            |
| ICT            | 20           | 2               |                            |
| Server Room    | 2 Admin PCs  |                 | 3 (DHCP, HTTP, and Email)  |

### Network Diagram
  ![TD Bank](https://github.com/user-attachments/assets/2a81e379-f1ef-47dc-820e-c29a3115c381)


### Requirements:
- Use any network simulation software to implement topology:
    - Simulation software: Packet tracer for design and implementation
    - There should be one router on each floor. The router should be connecting switches on that floor.
    - Use OSPF as the routing protocol to advertise routes.
    - Each department is required to have a wireless network for the users.
    - Each department except the server room will be anticipated to have around 60 users both wired and wireless users.
    - Host devices in the network are required to obtain IPv4 addresses automatically.
    - Devices in all the departments are required to communicate with each other.
    - All network devices are expected to dynamically obtain an IP address from the dedicated DHCP servers located in the server room.
    - Create HTTP and E-mail servers.
    - Configure SSH in all the routers for remote login.

- Use hierarchical network design with redundancy included:
    - Having core, distribution, and access layers.
      
- Configure the basic configuration of the devices:
    -Hostnames
    - Line console and VTP passwords
    - Banner messages
    - Disable domain IP lookup

- Each department should be in a different VLAN
    - Create VLANs in every department
    - VLANs you will use including VLAN1 also e.g. 10, 20, 30…etc
    - Each VLAN should be in a different subnetwork.

- Planning of IP Addresses:
    - You have been given 192.168.10.0 as the base address for this network.
    - Do subnetting based on the number of hosts in every department as provided above.
    - Identify the subnet mask, usable IP address range, and broadcast address for each subnet.

- End Device Configurations:
    - Configure all the end devices in the network with the appropriate IP address based on the calculation above.

- Configure port-security:
    - Use the sticky command to obtain the MAC Address.
    - Violation mode of the shutdown.
- Test Communication:
    - Do devices in the same VLAN communicate?
    - Do the devices in different VLANs communicate?


### Technologies Implemented
- Creating a network topology using Cisco Packet Tracer.
- Hierarchical Network Design.
- Connecting Networking devices with Correct cabling.
- Configuring Basic device settings.
- Creating VLANs and assigning ports VLAN numbers.
- Subnetting and IP Addressing.
- Configuring Inter-VLAN Routing on the Multilayer switches (Switch Virtual Interface).
- Configuring a Dedicated DHCP Server device to provide dynamic IP allocation.
- Configuring SSH for secure Remote access.
- Configuring OSPF as the routing protocol.
- Configuring switchport security or Port-Security on the switches.
- Configuring WLAN or wireless network (Cisco Access Point).
- Host Device Configurations.
- Test and Verifying Network Communication.

### IP Addressing 
### Base Network: 192.168.10.0
# Network Configuration

## [First Floor](pplx://action/followup)

| Department     | Network Address | Subnet Mask        | Host Address Range           | Broadcast Address |
|----------------|-----------------|--------------------|-----------------------------|-------------------|
| Management     | 192.168.10.0    | 255.255.255.192/26 | 192.168.10.1 - 192.168.10.62 | 192.168.10.63     |
| Research       | 192.168.10.64   | 255.255.255.192/26 | 192.168.10.65 - 192.168.10.126 | 192.168.10.127   |
| Human Resource | 192.168.10.128  | 255.255.255.192/26 | 192.168.10.129 - 192.168.10.190 | 192.168.10.191   |

## [Second Floor](pplx://action/followup)

| Department | Network Address | Subnet Mask        | Host Address Range           | Broadcast Address |
|------------|-----------------|--------------------|-----------------------------|-------------------|
| Marketing  | 192.168.10.192  | 255.255.255.192/26 | 192.168.10.193 - 192.168.10.254 | 192.168.10.255   |
| Accounts   | 192.168.11.0    | 255.255.255.192/26 | 192.168.11.1 - 192.168.11.62 | 192.168.11.63     |
| Finance    | 192.168.11.64   | 255.255.255.192/26 | 192.168.11.65 - 192.168.11.126 | 192.168.11.127   |

## [Third Floor](pplx://action/followup)

| Department | Network Address | Subnet Mask        | Host Address Range           | Broadcast Address |
|------------|-----------------|--------------------|-----------------------------|-------------------|
| Logistics  | 192.168.11.128  | 255.255.255.192/26 | 192.168.11.129 - 192.168.11.190 | 192.168.11.191   |
| Customer   | 192.168.11.192  | 255.255.255.192/26 | 192.168.11.193 - 192.168.11.254 | 192.168.11.255   |
| Guest      | 192.168.12.0    | 255.255.255.192/26 | 192.168.12.1 - 192.168.12.62 | 192.168.12.63     |

## [Fourth Floor](pplx://action/followup)

| Department  | Network Address | Subnet Mask        | Host Address Range           | Broadcast Address |
|-------------|-----------------|--------------------|-----------------------------|-------------------|
| Admin       | 192.168.12.64   | 255.255.255.192/26 | 192.168.12.65 - 192.168.12.126 | 192.168.12.127   |
| ICT         | 192.168.12.128  | 255.255.255.192/26 | 192.168.12.129 - 192.168.12.190 | 192.168.12.191   |
| Server Room | 192.168.12.192  | 255.255.255.192/26 | 192.168.12.193 - 192.168.12.254 | 192.168.12.255   |

# Network Configuration Between Routers and Layer-3 Switches

| NO. | Network Address | Subnet Mask     | Host Address Range        | Broadcast Address |
|-----|-----------------|-----------------|---------------------------|-------------------|
| 1   | 10.10.10.0      | 255.255.255.252 | 10.10.10.1 - 10.10.10.2   | 10.10.10.3        |
| 2   | 10.10.10.4      | 255.255.255.252 | 10.10.10.5 - 10.10.10.6   | 10.10.10.7        |
| 3   | 10.10.10.8      | 255.255.255.252 | 10.10.10.9 - 10.10.10.10  | 10.10.10.11       |
| 4   | 10.10.10.12     | 255.255.255.252 | 10.10.10.13 - 10.10.10.14 | 10.10.10.15       |
| 5   | 10.10.10.16     | 255.255.255.252 | 10.10.10.17 - 10.10.10.18 | 10.10.10.19       |
| 6   | 10.10.10.20     | 255.255.255.252 | 10.10.10.21 - 10.10.10.22 | 10.10.10.23       |
| 7   | 10.10.10.24     | 255.255.255.252 | 10.10.10.25 - 10.10.10.26 | 10.10.10.27       |
| 8   | 10.10.10.28     | 255.255.255.252 | 10.10.10.29 - 10.10.10.30 | 10.10.10.31       |
| 9   | 10.10.10.32     | 255.255.255.252 | 10.10.10.33 - 10.10.10.34 | 10.10.10.35       |
| 10  | 10.10.10.36     | 255.255.255.252 | 10.10.10.37 - 10.10.10.38 | 10.10.10.39       |
| 11  | 10.10.10.40     | 255.255.255.252 | 10.10.10.41 - 10.10.10.42 | 10.10.10.43       |
| 12  | 10.10.10.44     | 255.255.255.252 | 10.10.10.45 - 10.10.10.46 | 10.10.10.47       |
| 13  | 10.10.10.48     | 255.255.255.252 | 10.10.10.49 - 10.10.10.50 | 10.10.10.51       |
| 14  | 10.10.10.52     | 255.255.255.252 | 10.10.10.53 - 10.10.10.54 | 10.10.10.55       |



