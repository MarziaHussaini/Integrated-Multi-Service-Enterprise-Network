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
🔹 Access Points (APs):
Devices that broadcast wireless signals, allowing devices to connect to the network.
Example: In an office, APs are placed on each floor to provide Wi-Fi coverage.
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
