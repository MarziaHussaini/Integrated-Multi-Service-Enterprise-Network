<h1>Integrated Multi-Service Enterprise Network</h1>

<h2>Description</h2>


🔹 VLAN segments switch ports into separate virtual networks; trunk ports carry traffic for multiple VLANs using tags.

🔹 SSH provides secure, encrypted remote access to network devices, ensuring confidentiality, authentication, and integrity.

🔹 Standard ACL filters traffic based solely on source IP, e.g., blocking 192.168.1.0/24 to protect sensitive systems.

🔹 NAT translates private IPs to public IPs, allowing multiple devices to share one Internet address while hiding internal networks.

🔹 STP prevents Layer 2 loops by creating a loop-free topology through root bridge selection and path cost calculation.

🔹 PortFast enables immediate forwarding on access ports by bypassing STP delays—used only for end devices, not switch links.

🔹 BPDU Guard protects PortFast ports by disabling them upon receiving BPDUs, preventing accidental/malicious switch connections.

🔹 EtherChannel aggregates physical links into one logical link, increasing bandwidth and redundancy; STP treats it as a single link.

🔹 IP Address & Subnetting define device identity and network boundaries; the subnet mask separates network and host portions.

🔹 HSRP provides gateway redundancy by assigning active/standby roles to routers; failover ensures continuous connectivity.

🔹 LACP (IEEE 802.3ad) bundles physical links into a single logical interface for higher bandwidth and fault tolerance.

🔹 DHCP auto-assigns IP addresses and network settings (subnet, gateway, DNS) to clients for simplified configuration.

🔹 DHCP Helper (relay) forwards DHCP requests across subnets, enabling centralized IP assignment in routed networks.

🔹 DMZ is a secure zone between internal networks and the Internet, hosting public services while isolating critical systems.

🔹 Server Farm is a centralized group of servers providing scalable, redundant resources for applications and services.

🔹 OSPF is a dynamic routing protocol that calculates optimal paths and quickly adapts to network changes—ideal for large networks.

🔹 Wireless Network enables cable-free connectivity for mobile devices like laptops and smartphones.

🔹 Access Points (APs) broadcast Wi-Fi signals, connecting wireless devices to the network.

🔹 Wireless LAN Controller (WLC) centrally manages multiple APs, ensuring secure, seamless connectivity and roaming.

🔹 CAPWAP allows WLCs to control APs remotely and efficiently using a standardized protocol.

🔹 VoIP delivers voice communication over IP networks.

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

<B> Firewall (FWL1 & FWL2) Verification </B>


Firewall (FWL) Verification 


<img width="427" alt="Fw1" src="https://github.com/user-attachments/assets/e202f1cd-4dc0-4741-a900-e8225de5912d" />




Firewal2 (FWL) Verification 


<img width="416" alt="fw2" src="https://github.com/user-attachments/assets/8afd93a1-8a68-4d5c-bbf3-ec69c7c0d6de" />




CORE-SW1 Verification 



<img width="374" alt="SW1" src="https://github.com/user-attachments/assets/a0e256b5-4193-4de1-9742-1f18b8f57b41" />


CORE-SW2 Verification 




<img width="567" alt="SW2" src="https://github.com/user-attachments/assets/943ddf8e-4c55-4df7-b22d-b2ac2426cd9e" />





<B> Core Switches (CORE-SW1 and CORE-SW2) Verification  </B>

CORE-SW1 

<img width="412" height="478" alt="sw1 PING" src="https://github.com/user-attachments/assets/69637bda-4abb-4651-8744-6525fc948bb8" />








CORE-SW1

<img width="454" height="486" alt="sw1 PING 2" src="https://github.com/user-attachments/assets/1865496b-fb30-407d-974b-ad090a33516f" />







CORE-SW2

<img width="411" height="482" alt="PING 1" src="https://github.com/user-attachments/assets/c4208cc8-eb2f-40bc-9e70-e36ed60ba8f1" />








CORE-SW2

<img width="500" height="481" alt="PING 2" src="https://github.com/user-attachments/assets/18f0bde8-b2db-4d61-8fd9-1865208a5c54" />









<B> Routers (SEACOM & SAFARICOM) Verification  </B>





