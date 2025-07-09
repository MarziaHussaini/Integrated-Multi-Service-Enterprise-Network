<h1>Integrated Multi-Service Enterprise Network</h1>

<h2>Description</h2>


🔹 VLAN (Virtual Local Area Network) assignment groups switch ports to create separate virtual networks, while trunk ports connect switches and carry traffic for multiple VLANs using tags.

🔹SSH (Secure Shell) securely connects to network devices remotely by encrypting data and verifying users, ensuring safe management while meeting key security standards such as confidentiality, authentication, data integrity, and compliance.

🔹Standard Access Control List (ACL) A Standard ACL controls traffic by allowing or blocking it based only on the source IP address — for example, blocking all traffic coming from the IP range 192.168.1.0/24 to protect a sensitive server.

🔹 NAT converts private IPs to a public IP, letting multiple devices share one Internet address while keeping internal addresses hidden.

🔹 STP (Spanning Tree Protocol) prevents loops in Layer 2 networks by creating a loop-free topology. It selects a Root Bridge and calculates the best path to it based on path cost.

🔹 PortFast is a Cisco feature for access ports that lets them skip STP delays and forward traffic immediately. It's ideal for end devices like PCs or IP phones—never use it on trunk or switch links to avoid loops.

🔹 BPDU Guard enhances security on PortFast-enabled access ports by shutting down the port if a BPDU is received. This prevents accidental or malicious switch connections to user ports.

🔹 EtherChannel combines multiple physical links into one logical link to increase bandwidth, provide redundancy, and prevent loops (STP treats it as a single link.

🔹 IP Address and Subnetting – An IP address uniquely identifies a device on a network, allowing it to send and receive data. The subnet mask determines which portion of the IP address refers to the network and which to the host.

🔹 HSRP (Hot Standby Router Protocol) creates a virtual gateway by assigning one router as active and another as standby, ensuring network redundancy. If the active router fails, the standby takes over seamlessly, maintaining uninterrupted connectivity.

🔹 LACP (Link Aggregation Control Protocol) combines multiple physical links into one logical link (LAG) to increase bandwidth and ensure redundancy. It’s part of IEEE 802.3ad, allowing interoperability between network devices like switches, routers, and servers.

🔹 DHCP (Dynamic Host Configuration Protocol) is a network service that automatically assigns IP addresses and other network settings (like subnet mask, gateway, DNS) to devices on a network, enabling them to communicate without manual configuration.

🔹 DHCP Helper (also known as DHCP Relay) is a feature on routers or Layer 3 devices that forwards DHCP requests from clients in one subnet to a DHCP server located in another subnet. This allows centralized IP address management across multiple networks.

🔹 DMZ (Demilitarized Zone) is a physical or logical subnet that separates an organization’s internal network from untrusted external networks (like the Internet). It hosts public-facing services (such as web, email, and DNS servers) to provide controlled access while protecting the internal network from direct exposure to external threats.

🔹 Server Farm refers to a collection of servers housed together, often in the same data center or rack, working collectively to deliver large-scale computing resources, applications, or services. Server farms provide scalability, load balancing, and redundancy for critical applications.

🔹 OSPF is a dynamic routing protocol that helps routers share and learn routes automatically. It finds the best, shortest path quickly and updates routes fast if a link fails, making it ideal for large networks.

🔹 Wireless Network allows devices like laptops, smartphones, and tablets to connect to a network without physical cables. 

🔹 Access Points (APs): Devices that broadcast wireless signals, allowing devices to connect to the network. Like, In an office, APs are placed on each floor to provide Wi-Fi coverage.

🔹 Wireless LAN Controller (WLC) A central device that manages multiple access points (APs) to ensure secure, seamless, and efficient wireless connectivity. It handles network access, user authentication, and smooth roaming between APs. With a WLC, employees can move between floors without losing their Wi-Fi connection.

🔹 CAPWAP is a protocol that allows a Wireless LAN Controller (WLC) to manage Access Points (APs) automatically.

🔹 VoIP (Voice over Internet Protocol) VoIP allows voice calls over IP networks (like the internet or company LAN) instead of traditional phone lines.

<br />


<h2>CONFIG STEPS</h2>
- <b> Network Architecture Diagram </b> 

- <b> Basic settings to all devices + SSH + Standard ACL for SSH </b>

- <b> VLAN assignment plus all access and trunk ports on l2 and l3 switches </b>

- <b> STP Portfast and BPDUguard configs on all access ports </b>

- <b> EtherChannel </b>

- <b> Subnetting and IP addressing </b>

- <b> HSRP and Inter-VLAN routing on the l3 switches plus ip dhcp helper addresses</b>

- <b> Static IP address to DMZ/server farm devices</b>

- <b> DHCP server device configurations </b>

- <b> OSPF on the firewall, routers, and switches </b>

- <b> Firewall interface security zones and levels </b>

- <b> Firewall routing-OSPF + Static Routes </b>

- <b> Firewall inspection policy configuration </b>

- <b> Wireless network configurations </b>

- <b> VOIP Configs </b>

- <b> Verifying and testing configurations </b>

<h2>Tools and Utilities Used</h2>

- <b>VLANs</b> 
- <b>SSH</b>
- <b> ACL </b>
- <b> NAT </b>
- <b> STP </b>
- <b> PortFast </b>
- <b> BPDU </b> 
- <b> EtherChannel </b>
- <b> IP Address and Subnetting </b>
- <b> HSRP </b>
- <b> LACP </b>
- <b> DHCP </b>
- <b> DHCP Helper </b>
- <b> DMZ </b>
- <b> Server Farm </b>
- <b> OSPF </b>
- <b> Wireless Network </b>
- <b> APs </b>
- <b> WLC </b>
- <b> CAPWAP </b>
- <b> VoIP </b>


<h2>Environments Used </h2>

- <b>Windows 11</b> 
- <b>Cisco Packet Tracer </b>

<h2>Network diagram</h2>



<img width="597" alt="Final p" src="https://github.com/user-attachments/assets/6fd06226-43fd-4609-ae12-53bac64546df" />



<h2>Program walk-through</h2>

<b>Open Cisco Packet Tracer </b>

<b> Devices Used <b>

- <b> PCs, IP Phones, Printer, Tablet, smartphone, and APs<b>
- <b> 6 Layer 2 Switches and 2 Switches layer 3(HSRP, LACP and routing) <b>
- <b> 2 Firewall (Blocks threats and allows safe traffic) <b>
- <b> DMZ (Web, FTP, E-Mail, APP & NAS) <b>
- <b> 2 ISP, CLOUD, USA-USER, & CHINA-USER <b>
- <b> SERVER (DHCP, RADIUS, & DNS) <b>
- <b> 1 ROUTER for voice Gateway, PC for configuration of Wireless LAN Controller <b>
- <b> Crossover and straight-through cables were used to connect the devices<b>

<b> VLAN & IP Addressing <b>

<b> Each group of PCs is isolated logically using VLANs to segment traffic and improve security/performance <b>

VALN 10
 - <b> Subnet: 192.168.10.0/24<b>
- <b>Subnet Mask: 255.255.255.0<b>
 - <b> Default Gateway: 192.168.10.100<b>
 - <b> Address Type: DHCP<b>
- <b> Purpose: Management VLAN (Switches, WLC, AP) <b>

VALN 20
- <b> Subnet: 172.16.0.0/16<b>
- <b>Subnet Mask: 255.255.0.0 <b>
 - <b> Default Gateway: 172.16.0.1<b>
 - <b> Address Type: DHCP<b>
- <b> Purpose: connected to User LAN (PCs, printers) <b>


VALN 50
- <b> Subnet: 10.20.0.0/16<b>
- <b>Subnet Mask: 255.255.0.0 <b>
 - <b> Default Gateway: 10.20.0.1<b>
 - <b> Address Type: DHCP<b>
- <b> Purpose: Wireless LAN (Clients via APs) <b>

VALN 70
- <b> Subnet: 172.30.0.0/16<b>
- <b>Subnet Mask: 255.255.0.0 <b>
 - <b> Default Gateway: 172.30.0.1<b>
 - <b> Address Type: DHCP<b>
- <b> Purpose: VoIP / IP Phones<b>

VALN 90
- <b> Subnet: 10.11.11.32/27<b>
- <b>Subnet Mask: 255.255.255.224<b>
 - <b> Default Gateway: 10.11.11.33<b>
 - <b> Address Type: DHCP<b>
- <b> Purpose: DMZ / Internal Servers<b>

<b> VLAN Diagram </b>

<img width="879" alt="LAN DIAGRAM" src="https://github.com/user-attachments/assets/ae1576c1-2d90-4166-9b4d-8d98c33eec23" />


<b> CORE-SW1 <b>

Interface-Gi1/0/1
- <b> IP Address: 10.2.2.1<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
 - <b> Purpose / Role: Connects to FWL1 (Inside)<b>

 Interface-Gi1/0/2
- <b> IP Address: 10.2.2.5<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
 - <b> Purpose / Role: Connects to FWL2 (Inside)<b>

Interface- VLAN 10 (SVI)
- <b> IP Address: 192.168.10.3<b>
- <b> Gateway: 192.168.10.100<b>
 - <b> Subnet Mask: 255.255.255.0 /24<b>
 - <b> Purpose / Role: Management VLAN – switches, WLC, APs<b>
 
Interface- VLAN 20 (SVI)
- <b> IP Address: 172.16.0.3<b>
- <b> Gateway: 172.16.0.1<b>
 - <b> Subnet Mask: 255.255.0.0 /16<b>
 - <b> Purpose / Role: User LAN VLAN – PCs, printers<b>

Interface- VLAN 50 (SVI)
- <b> IP Address: 10.20.0.2<b>
- <b> Gateway: 10.20.0.1<b>
 - <b> Subnet Mask: 255.255.0.0 /16<b>
 - <b> Purpose / Role: Wireless VLAN – AP clients<b>

Interface- VLAN 90 (SVI)
- <b> IP Address: 10.11.11.34<b>
- <b> Gateway: 10.11.11.33<b>
 - <b> Subnet Mask: 255.255.255.224 /27<b>
 - <b> Purpose / Role: Server VLAN / DMZ Access – connects to FWL1 Gi1/5<b>

<b> CORE-SW2 </b>

Interface-Gi1/0/1
- <b> IP Address: 10.2.2.13<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
 - <b> Purpose / Role: Connects to FWL2 (Inside)<b>

 Interface-Gi1/0/2
- <b> IP Address: 10.2.2.9<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
 - <b> Purpose / Role: Connects to FWL1(Inside)<b>

Interface- VLAN 10 (SVI)
- <b> IP Address: 192.168.10.2<b>
- <b> Gateway: 192.168.10.100<b>
 - <b> Subnet Mask: 255.255.255.0 /24<b>
 - <b> Purpose / Role: Management VLAN – switches, WLC, APs<b>
 
Interface- VLAN 20 (SVI)
- <b> IP Address: 172.16.0.2<b>
- <b> Gateway: 172.16.0.1<b>
 - <b> Subnet Mask: 255.255.0.0 /16<b>
 - <b> Purpose / Role: User LAN VLAN – PCs, printers<b>

Interface- VLAN 50 (SVI)
- <b> IP Address: 10.20.0.3<b>
- <b> Gateway: 10.20.0.1<b>
 - <b> Subnet Mask: 255.255.0.0 /16<b>
 - <b> Purpose / Role: Wireless VLAN – AP clients<b>

Interface- VLAN 90 (SVI)
- <b> IP Address: 10.11.11.35<b>
- <b> Gateway: 10.11.11.33<b>
 - <b> Subnet Mask: 255.255.255.224 /27<b>
 - <b> Purpose / Role: Server VLAN / DMZ Access – connects to FWL1 Gi1/5<b>

<b>SW1-2 diagram</b>


<img width="841" alt="sw-12 final " src="https://github.com/user-attachments/assets/98b1a01a-cd2d-4828-a924-1764bbc118c2" />




<b> FWL1 – Firewall 1 (Primary Firewall)</b>

Interface-Gi1/1
- <b> IP Address: 105.100.50.2<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 105.100.50.1<b>
 - <b> Purpose / Role: ISP1 Internet Uplink<b>

 Interface-Gi1/2
- <b> IP Address: 197.200.100.2<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 197.200.100.1<b>
 - <b> Purpose / Role: ISP2 Backup Internet Uplink<b>

Interface-Gi1/3
- <b> IP Address: 10.2.2.2<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 10.2.2.1<b>
 - <b> Purpose / Role: Inside (Trusted Zone) – Core SW1<b>
 
Interface-Gi1/4
- <b> IP Address: 10.2.2.10<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 10.2.2.9<b>
 - <b> Purpose / Role: Inside (Trusted Zone) – Core SW2<b>

Interface-Gi1/5
- <b> IP Address: 10.11.11.1<b>
 - <b> Subnet Mask: 255.255.255.224 /27<b>
- <b> Gateway: 10.11.11.33<b>
 - <b> Purpose / Role: DMZ (Web, DNS, Mail Servers)<b>

<b> FWL2 – Firewall 2 (Secondary / Backup Firewall)</b>

Interface-Gi1/1
- <b> IP Address: 105.100.50.6<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 105.100.50.5<b>
 - <b> Purpose / Role: Backup ISP1 Internet Uplink<b>

 Interface-Gi1/2
- <b> IP Address: 197.200.100.6<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 197.200.100.5<b>
 - <b> Purpose / Role: Backup ISP2 Internet Uplink<b>

Interface-Gi1/3
- <b> IP Address: 10.2.2.6<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 10.2.2.5<b>
 - <b> Purpose / Role: Inside (Trusted Zone) – Core SW1<b>

Interface-Gi1/4
- <b> IP Address: 10.2.2.14<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Gateway: 10.2.2.13<b>
 - <b> Purpose / Role: Inside (Trusted Zone) – Core SW2<b>

Interface-Gi1/5
- <b> IP Address: 10.11.11.2<b>
 - <b> Subnet Mask: 255.255.255.224 /27<b>
- <b> Gateway: 10.11.11.34<b>
 - <b> Purpose / Role: DMZ – Redundant Interface<b>

<b>FWL1-2 diagram</b>


<img width="486" alt="firwal" src="https://github.com/user-attachments/assets/29f5f6cf-5ab9-4d8c-8709-0ab6b396bd35" />





<b>SEACOM-ISP</b>

Interface-Gi0/0
- <b> IP Address: 105.100.50.1<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Purpose / Role: Connection to Firewall 1 (FWL1)<b>

<b>SEACOM-ISP</b>

Interface-Gi0/1
- <b> IP Address: 105.100.50.5<b>
 - <b> Subnet Mask: 255.255.255.252 /30<b>
- <b> Purpose / Role: Connection to Firewall 2 (FWL2) or backup link<b>

<b>ISP 1-2 diagram</b>


<img width="441" alt="ISP" src="https://github.com/user-attachments/assets/bbf5d504-ccfb-4b6d-bb55-575c727cdcc0" />




<b> Cisco Voice Gateway</b>

- <b> VLAN 70 (VoIP VLAN)<b>
 - <b> Subnet: 172.30.0.0/16<b>
- <b> Default Gateway: 172.30.0.1<b>
- <b> Connected Devices: IP Phones, possibly Call Manager (CUCM), and switches<b>
- <b> Purpose / Role: Acts as the SIP/H.323 gateway for internal phones to communicate externally<b>

<b> Cisco Wireless LAN Controller (WLC)</b>

- <b> VLAN 50 (Wireless LAN)<b>
 - <b> Subnet: 10.20.0.0/16<b>
- <b> Default Gateway: 10.20.0.1<b>
- <b> Connected Devices: Access Points (APs), Wireless Clients (Phones, Laptops)<b>
- <b> Purpose / Role: Manages all corporate wireless access; authenticates wireless clients<b>

<b> Net-Sec PC (Network Security PC)</b>

- <b> VLAN 90 (DMZ/Internal Services)<b>
 - <b> Subnet: 10.11.11.32/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Connected Devices: Firewalls (FWL1, FWL2), DMZ servers<b>
- <b> Purpose: Monitors firewall logs, IDS/IPS, and other security platforms<b>


<b> Voice Gateway , WLC  & Net-Sec PC Diagram </b>


<img width="541" alt="gatway" src="https://github.com/user-attachments/assets/7ff6c583-3dba-4735-b053-cf8ec013747b" />






<B> DMZ / SERVER FARM </B>

Network Storage (SAN)
- <b>IP Adress: 10.11.11.23<b>
 - <b> Subnet: 10.11.11.0/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Purpose: Stores files, backups, shared<b>

Application Server (APP)
- <b>IP Adress: 10.11.11.24<b>
 - <b> Subnet: 10.11.11.0/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Purpose: Hosts enterprise apps used by clients/users<b>

Mail Server (MAIL)
- <b>IP Adress: 10.11.11.22<b>
 - <b> Subnet: 10.11.11.0/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Purpose: Handles corporate email<b>

File Server (FTP)
- <b>IP Adress: 10.11.11.20<b>
 - <b> Subnet: 10.11.11.0/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Purpose: Serves internal/external file requests<b>

Web Server (WEB)
- <b>IP Adress: 10.11.11.21<b>
 - <b> Subnet: 10.11.11.0/27<b>
- <b> Default Gateway: 10.11.11.33<b>
- <b> Purpose: Hosts internal/external websites<b>


<B> DMZ / SERVER FARM DIAGRAM</B>


<img width="481" alt="NEW DMZ" src="https://github.com/user-attachments/assets/ba6077c8-03dc-4c3d-b141-bc29a45822f4" />


<B> External User & Cloud </B>
China User
- <b>IP Adress: 8.0.0.20<b>
 - <b> Subnet Mask: 255.0.0.0 /8<b>
- <b> Gateway: 30.30.30.30<b>
- <b> Role: Remote User <b>
- <b> Purpose: Access internal services (App, Web, VoIP, etc.) via Internet (possibly VPN) <b>

USA User
- <b>IP Adress: 8.0.0.10<b>
 - <b> Subnet Mask: 255.0.0.0 /8<b>
- <b> Gateway: 20.20.20.20 <b>
- <b> Role: Remote User <b>
- <b> Purpose: Access internal systems securely (VPN/Web/App/Voice)<b>

Cloud
- <b>IP Adress: 20.20.20.2/30.30.30.2<b>
 - <b> Subnet Mask: 255.255.255.252/30<b>
- <b> Gateway: 20.20.20.1/30.30.30.1 <b>
- <b> Role: External Cloud Server<b>
- <b> Purpose: Provides hosted services (VoIP trunk, backup, DNS, cloud apps, etc.) <b>


<B> External User & Cloud Diagram</B>


<img width="560" alt="cloud" src="https://github.com/user-attachments/assets/64c7ae66-0c37-4cb2-a625-3e33cfdd15bd" />














<B> Verified configuration diagram</B>



