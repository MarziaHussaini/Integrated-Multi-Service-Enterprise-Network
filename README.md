<h1>Integrated Multi-Service Enterprise Network</h1>

<h2>Description</h2>

<p>
This project implements a comprehensive enterprise network architecture incorporating VLANs, secure remote access, routing, switching, IP addressing, wireless, VoIP, and firewall policies. Below is a breakdown of the key technologies and their roles:
</p>

<ul>
  <li><b>VLAN:</b> Segments switch ports into separate broadcast domains; trunk ports carry traffic for multiple VLANs using tagging.</li>
  <li><b>SSH:</b> Enables encrypted remote access to network devices, ensuring confidentiality, integrity, and authentication.</li>
  <li><b>Standard ACL:</b> Filters traffic based on source IP address—for example, blocking 192.168.1.0/24 to secure critical systems.</li>
  <li><b>NAT:</b> Translates private IPs to public IPs, allowing multiple devices to share a single Internet IP while hiding internal addresses.</li>
  <li><b>STP:</b> Prevents Layer 2 loops by creating a loop-free topology using root bridge election and path cost calculation.</li>
  <li><b>PortFast:</b> Bypasses STP delays on access ports, allowing end devices to connect instantly. Not used on uplinks.</li>
  <li><b>BPDU Guard:</b> Disables PortFast-enabled ports if BPDUs are received, protecting against rogue switch connections.</li>
  <li><b>EtherChannel:</b> Aggregates multiple physical links into one logical link for increased bandwidth and redundancy; STP treats it as a single path.</li>
  <li><b>IP Addressing & Subnetting:</b> Defines device identities and network boundaries using subnet masks to differentiate host and network portions.</li>
  <li><b>HSRP:</b> Provides gateway redundancy by assigning active/standby roles to routers; enables seamless failover for high availability.</li>
  <li><b>LACP (802.3ad):</b> Dynamically bundles multiple physical links into a logical interface for load balancing and fault tolerance.</li>
  <li><b>DHCP:</b> Automatically assigns IP addresses and configuration (gateway, DNS) to clients for simplified setup.</li>
  <li><b>DHCP Relay (Helper):</b> Forwards DHCP requests across subnets, enabling centralized IP address assignment in routed environments.</li>
  <li><b>DMZ:</b> A semi-secure zone between the internal network and the Internet, typically used to host public-facing services.</li>
  <li><b>Server Farm:</b> Centralized group of servers providing scalable and redundant services and applications.</li>
  <li><b>OSPF:</b> A dynamic routing protocol used to compute the shortest path and adapt to network changes, ideal for large networks.</li>
  <li><b>Wireless Network:</b> Enables wireless access for mobile clients such as laptops and smartphones.</li>
  <li><b>Access Points (APs):</b> Broadcast wireless signals to connect end-user devices to the wired LAN.</li>
  <li><b>Wireless LAN Controller (WLC):</b> Centrally manages APs, providing secure, scalable wireless deployment with seamless roaming.</li>
  <li><b>CAPWAP:</b> A protocol that allows centralized management of APs by WLCs over Layer 3 networks.</li>
  <li><b>VoIP:</b> Delivers voice communication over IP networks, reducing costs and enabling unified communications.</li>
</ul>

<h2>Configuration Steps</h2>
<ol>
  <li><b>Network Architecture Diagram</b></li>
  <li><b>Initial Setup:</b> Basic settings, SSH configuration, and standard ACL for secure device access.</li>
  <li><b>VLAN Configuration:</b> Assign access and trunk ports on Layer 2 and Layer 3 switches.</li>
  <li><b>STP Enhancements:</b> Apply PortFast and BPDU Guard to all access ports.</li>
  <li><b>EtherChannel:</b> Configure link aggregation between switches and/or routers.</li>
  <li><b>IP Addressing & Subnetting:</b> Allocate IP ranges and configure devices accordingly.</li>
  <li><b>HSRP & Inter-VLAN Routing:</b> Enable gateway redundancy and route between VLANs on L3 switches; add DHCP relay addresses.</li>
  <li><b>Static IPs:</b> Assign static IP addresses to DMZ and server farm devices.</li>
  <li><b>DHCP Server Configuration:</b> Set scopes and options for automatic IP assignment.</li>
  <li><b>OSPF Configuration:</b> Enable dynamic routing on firewalls, routers, and switches.</li>
  <li><b>Firewall Zones:</b> Define interface zones and assign security levels.</li>
  <li><b>Firewall Routing:</b> Configure static routes and OSPF for redundancy.</li>
  <li><b>Firewall Policies:</b> Apply stateful inspection and ACLs.</li>
  <li><b>Wireless Configuration:</b> Set up APs, WLC, and SSIDs.</li>
  <li><b>VoIP Configuration:</b> Assign IP phones, voice VLANs, and QoS policies.</li>
  <li><b>Testing & Validation:</b> Verify functionality and troubleshoot as needed.</li>
</ol>

<h2>Tools and Technologies Used</h2>
<ul>
  <li><b>VLANs</b></li>
  <li><b>SSH</b></li>
  <li><b>ACL</b></li>
  <li><b>NAT</b></li>
  <li><b>STP</b></li>
  <li><b>PortFast</b></li>
  <li><b>BPDU Guard</b></li>
  <li><b>EtherChannel</b></li>
  <li><b>IP Addressing & Subnetting</b></li>
  <li><b>HSRP</b></li>
  <li><b>LACP</b></li>
  <li><b>DHCP & DHCP Helper</b></li>
  <li><b>DMZ</b></li>
  <li><b>Server Farm</b></li>
  <li><b>OSPF</b></li>
  <li><b>Wireless Networking</b></li>
  <li><b>Access Points (APs)</b></li>
  <li><b>Wireless LAN Controller (WLC)</b></li>
  <li><b>CAPWAP</b></li>
  <li><b>VoIP</b></li>
</ul>

<h2>Environments Used</h2>
<ul>
  <li><b>Windows 11</b></li>
  <li><b>Cisco Packet Tracer</b></li>
</ul>


<h2>Network diagram</h2>



<img width="597" alt="Final p" src="https://github.com/user-attachments/assets/6fd06226-43fd-4609-ae12-53bac64546df" />



<h2>Program Walk-through</h2>

<p><b>Open Cisco Packet Tracer</b></p>

<h3>Devices Used</h3>
<ul>
  <li><b>PCs, IP Phones, Printers, Tablets, Smartphones, and Access Points (APs)</b></li>
  <li><b>6 Layer 2 Switches and 2 Layer 3 Switches (with HSRP, LACP, and Routing)</b></li>
  <li><b>2 Firewalls (Block threats and allow safe traffic)</b></li>
  <li><b>DMZ (Web, FTP, E-Mail, APP & NAS servers)</b></li>
  <li><b>2 ISPs, Cloud, USA-User, and China-User networks</b></li>
  <li><b>Server (DHCP, RADIUS, and DNS)</b></li>
  <li><b>1 Router for Voice Gateway and PC for Wireless LAN Controller configuration</b></li>
  <li><b>Crossover and straight-through cables used to connect devices</b></li>
</ul>

<h3>VLAN & IP Addressing</h3>
<p><b>Each group of devices is logically isolated using VLANs to segment traffic, enhancing security and performance.</b></p>

<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>VLAN</th>
      <th>Subnet</th>
      <th>Subnet Mask</th>
      <th>Default Gateway</th>
      <th>Address Type</th>
      <th>Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>VLAN 10</td>
      <td>192.168.10.0/24</td>
      <td>255.255.255.0</td>
      <td>192.168.10.100</td>
      <td>DHCP</td>
      <td>Management VLAN (Switches, WLC, APs)</td>
    </tr>
    <tr>
      <td>VLAN 20</td>
      <td>172.16.0.0/16</td>
      <td>255.255.0.0</td>
      <td>172.16.0.1</td>
      <td>DHCP</td>
      <td>User LAN (PCs, Printers)</td>
    </tr>
    <tr>
      <td>VLAN 50</td>
      <td>10.20.0.0/16</td>
      <td>255.255.0.0</td>
      <td>10.20.0.1</td>
      <td>DHCP</td>
      <td>Wireless LAN (Clients via APs)</td>
    </tr>
    <tr>
      <td>VLAN 70</td>
      <td>172.30.0.0/16</td>
      <td>255.255.0.0</td>
      <td>172.30.0.1</td>
      <td>DHCP</td>
      <td>VoIP / IP Phones</td>
    </tr>
    <tr>
      <td>VLAN 90</td>
      <td>10.11.11.32/27</td>
      <td>255.255.255.224</td>
      <td>10.11.11.33</td>
      <td>DHCP</td>
      <td>DMZ / Internal Servers</td>
    </tr>
  </tbody>
</table>

<p><b>VLAN Diagram</b></p>

<img width="879" alt="LAN DIAGRAM" src="https://github.com/user-attachments/assets/ae1576c1-2d90-4166-9b4d-8d98c33eec23" />


<h2>CORE-SW1</h2>

<ul>
  <li><b>Interface Gi1/0/1</b>
    <ul>
      <li>IP Address: 10.2.2.1</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connects to FWL1 (Inside)</li>
    </ul>
  </li>

  <li><b>Interface Gi1/0/2</b>
    <ul>
      <li>IP Address: 10.2.2.5</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connects to FWL2 (Inside)</li>
    </ul>
  </li>

  <li><b>Interface VLAN 10 (SVI)</b>
    <ul>
      <li>IP Address: 192.168.10.3</li>
      <li>Gateway: 192.168.10.100</li>
      <li>Subnet Mask: 255.255.255.0 (/24)</li>
      <li>Purpose / Role: Management VLAN – switches, WLC, APs</li>
    </ul>
  </li>

  <li><b>Interface VLAN 20 (SVI)</b>
    <ul>
      <li>IP Address: 172.16.0.3</li>
      <li>Gateway: 172.16.0.1</li>
      <li>Subnet Mask: 255.255.0.0 (/16)</li>
      <li>Purpose / Role: User LAN VLAN – PCs, printers</li>
    </ul>
  </li>

  <li><b>Interface VLAN 50 (SVI)</b>
    <ul>
      <li>IP Address: 10.20.0.2</li>
      <li>Gateway: 10.20.0.1</li>
      <li>Subnet Mask: 255.255.0.0 (/16)</li>
      <li>Purpose / Role: Wireless VLAN – AP clients</li>
    </ul>
  </li>

  <li><b>Interface VLAN 90 (SVI)</b>
    <ul>
      <li>IP Address: 10.11.11.34</li>
      <li>Gateway: 10.11.11.33</li>
      <li>Subnet Mask: 255.255.255.224 (/27)</li>
      <li>Purpose / Role: Server VLAN / DMZ Access – connects to FWL1 Gi1/5</li>
    </ul>
  </li>
</ul>

<h2>CORE-SW2</h2>

<ul>
  <li><b>Interface Gi1/0/1</b>
    <ul>
      <li>IP Address: 10.2.2.13</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connects to FWL2 (Inside)</li>
    </ul>
  </li>

  <li><b>Interface Gi1/0/2</b>
    <ul>
      <li>IP Address: 10.2.2.9</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connects to FWL1 (Inside)</li>
    </ul>
  </li>

  <li><b>Interface VLAN 10 (SVI)</b>
    <ul>
      <li>IP Address: 192.168.10.2</li>
      <li>Gateway: 192.168.10.100</li>
      <li>Subnet Mask: 255.255.255.0 (/24)</li>
      <li>Purpose / Role: Management VLAN – switches, WLC, APs</li>
    </ul>
  </li>

  <li><b>Interface VLAN 20 (SVI)</b>
    <ul>
      <li>IP Address: 172.16.0.2</li>
      <li>Gateway: 172.16.0.1</li>
      <li>Subnet Mask: 255.255.0.0 (/16)</li>
      <li>Purpose / Role: User LAN VLAN – PCs, printers</li>
    </ul>
  </li>

  <li><b>Interface VLAN 50 (SVI)</b>
    <ul>
      <li>IP Address: 10.20.0.3</li>
      <li>Gateway: 10.20.0.1</li>
      <li>Subnet Mask: 255.255.0.0 (/16)</li>
      <li>Purpose / Role: Wireless VLAN – AP clients</li>
    </ul>
  </li>

  <li><b>Interface VLAN 90 (SVI)</b>
    <ul>
      <li>IP Address: 10.11.11.35</li>
      <li>Gateway: 10.11.11.33</li>
      <li>Subnet Mask: 255.255.255.224 (/27)</li>
      <li>Purpose / Role: Server VLAN / DMZ Access – connects to FWL1 Gi1/5</li>
    </ul>
  </li>
</ul>

<h3>SW1-2 Diagram</h3>



<img width="841" alt="sw-12 final " src="https://github.com/user-attachments/assets/98b1a01a-cd2d-4828-a924-1764bbc118c2" />



<h2>FWL1 – Firewall 1 (Primary Firewall)</h2>

<ul>
  <li><b>Interface Gi1/1</b>
    <ul>
      <li>IP Address: 105.100.50.2</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 105.100.50.1</li>
      <li>Purpose / Role: ISP1 Internet Uplink</li>
    </ul>
  </li>

  <li><b>Interface Gi1/2</b>
    <ul>
      <li>IP Address: 197.200.100.2</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 197.200.100.1</li>
      <li>Purpose / Role: ISP2 Backup Internet Uplink</li>
    </ul>
  </li>

  <li><b>Interface Gi1/3</b>
    <ul>
      <li>IP Address: 10.2.2.2</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 10.2.2.1</li>
      <li>Purpose / Role: Inside (Trusted Zone) – Core SW1</li>
    </ul>
  </li>

  <li><b>Interface Gi1/4</b>
    <ul>
      <li>IP Address: 10.2.2.10</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 10.2.2.9</li>
      <li>Purpose / Role: Inside (Trusted Zone) – Core SW2</li>
    </ul>
  </li>

  <li><b>Interface Gi1/5</b>
    <ul>
      <li>IP Address: 10.11.11.1</li>
      <li>Subnet Mask: 255.255.255.224 (/27)</li>
      <li>Gateway: 10.11.11.33</li>
      <li>Purpose / Role: DMZ (Web, DNS, Mail Servers)</li>
    </ul>
  </li>
</ul>

<h2>FWL2 – Firewall 2 (Secondary / Backup Firewall)</h2>

<ul>
  <li><b>Interface Gi1/1</b>
    <ul>
      <li>IP Address: 105.100.50.6</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 105.100.50.5</li>
      <li>Purpose / Role: Backup ISP1 Internet Uplink</li>
    </ul>
  </li>

  <li><b>Interface Gi1/2</b>
    <ul>
      <li>IP Address: 197.200.100.6</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 197.200.100.5</li>
      <li>Purpose / Role: Backup ISP2 Internet Uplink</li>
    </ul>
  </li>

  <li><b>Interface Gi1/3</b>
    <ul>
      <li>IP Address: 10.2.2.6</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 10.2.2.5</li>
      <li>Purpose / Role: Inside (Trusted Zone) – Core SW1</li>
    </ul>
  </li>

  <li><b>Interface Gi1/4</b>
    <ul>
      <li>IP Address: 10.2.2.14</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 10.2.2.13</li>
      <li>Purpose / Role: Inside (Trusted Zone) – Core SW2</li>
    </ul>
  </li>

  <li><b>Interface Gi1/5</b>
    <ul>
      <li>IP Address: 10.11.11.2</li>
      <li>Subnet Mask: 255.255.255.224 (/27)</li>
      <li>Gateway: 10.11.11.34</li>
      <li>Purpose / Role: DMZ – Redundant Interface</li>
    </ul>
  </li>
</ul>

<h3>FWL1-2 Diagram</h3>




<img width="486" alt="firwal" src="https://github.com/user-attachments/assets/29f5f6cf-5ab9-4d8c-8709-0ab6b396bd35" />





<h2>SEACOM-ISP</h2>

<ul>
  <li><b>Interface Gi0/0</b>
    <ul>
      <li>IP Address: 105.100.50.1</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connection to Firewall 1 (FWL1)</li>
    </ul>
  </li>

  <li><b>Interface Gi0/1</b>
    <ul>
      <li>IP Address: 105.100.50.5</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Purpose / Role: Connection to Firewall 2 (FWL2) or backup link</li>
    </ul>
  </li>
</ul>

<h3>ISP 1-2 Diagram</h3>




<img width="441" alt="ISP" src="https://github.com/user-attachments/assets/bbf5d504-ccfb-4b6d-bb55-575c727cdcc0" />




<h2>Cisco Voice Gateway</h2>
<ul>
  <li><b>VLAN 70 (VoIP VLAN)</b></li>
  <ul>
    <li>Subnet: 172.30.0.0/16</li>
    <li>Default Gateway: 172.30.0.1</li>
    <li>Connected Devices: IP Phones, possibly Call Manager (CUCM), and switches</li>
    <li>Purpose / Role: Acts as the SIP/H.323 gateway for internal phones to communicate externally</li>
  </ul>
</ul>

<h2>Cisco Wireless LAN Controller (WLC)</h2>
<ul>
  <li><b>VLAN 50 (Wireless LAN)</b></li>
  <ul>
    <li>Subnet: 10.20.0.0/16</li>
    <li>Default Gateway: 10.20.0.1</li>
    <li>Connected Devices: Access Points (APs), Wireless Clients (Phones, Laptops)</li>
    <li>Purpose / Role: Manages all corporate wireless access; authenticates wireless clients</li>
  </ul>
</ul>

<h2>Net-Sec PC (Network Security PC)</h2>
<ul>
  <li><b>VLAN 90 (DMZ/Internal Services)</b></li>
  <ul>
    <li>Subnet: 10.11.11.32/27</li>
    <li>Default Gateway: 10.11.11.33</li>
    <li>Connected Devices: Firewalls (FWL1, FWL2), DMZ servers</li>
    <li>Purpose: Monitors firewall logs, IDS/IPS, and other security platforms</li>
  </ul>
</ul>

<h3>Voice Gateway, WLC & Net-Sec PC Diagram</h3>



<img width="541" alt="gatway" src="https://github.com/user-attachments/assets/7ff6c583-3dba-4735-b053-cf8ec013747b" />






<h2>DMZ / Server Farm</h2>

<ul>
  <li><b>Network Storage (SAN)</b>
    <ul>
      <li>IP Address: 10.11.11.23</li>
      <li>Subnet: 10.11.11.0/27</li>
      <li>Default Gateway: 10.11.11.33</li>
      <li>Purpose: Stores files, backups, shared resources</li>
    </ul>
  </li>

  <li><b>Application Server (APP)</b>
    <ul>
      <li>IP Address: 10.11.11.24</li>
      <li>Subnet: 10.11.11.0/27</li>
      <li>Default Gateway: 10.11.11.33</li>
      <li>Purpose: Hosts enterprise applications used by clients/users</li>
    </ul>
  </li>

  <li><b>Mail Server (MAIL)</b>
    <ul>
      <li>IP Address: 10.11.11.22</li>
      <li>Subnet: 10.11.11.0/27</li>
      <li>Default Gateway: 10.11.11.33</li>
      <li>Purpose: Handles corporate email</li>
    </ul>
  </li>

  <li><b>File Server (FTP)</b>
    <ul>
      <li>IP Address: 10.11.11.20</li>
      <li>Subnet: 10.11.11.0/27</li>
      <li>Default Gateway: 10.11.11.33</li>
      <li>Purpose: Serves internal and external file requests</li>
    </ul>
  </li>

  <li><b>Web Server (WEB)</b>
    <ul>
      <li>IP Address: 10.11.11.21</li>
      <li>Subnet: 10.11.11.0/27</li>
      <li>Default Gateway: 10.11.11.33</li>
      <li>Purpose: Hosts internal and external websites</li>
    </ul>
  </li>
</ul>

<h3>DMZ / Server Farm Diagram</h3>




<img width="481" alt="NEW DMZ" src="https://github.com/user-attachments/assets/ba6077c8-03dc-4c3d-b141-bc29a45822f4" />


<h2>External User & Cloud</h2>

<ul>
  <li><b>China User</b>
    <ul>
      <li>IP Address: 8.0.0.20</li>
      <li>Subnet Mask: 255.0.0.0 (/8)</li>
      <li>Gateway: 30.30.30.30</li>
      <li>Role: Remote User</li>
      <li>Purpose: Access internal services (App, Web, VoIP, etc.) via Internet (possibly VPN)</li>
    </ul>
  </li>

  <li><b>USA User</b>
    <ul>
      <li>IP Address: 8.0.0.10</li>
      <li>Subnet Mask: 255.0.0.0 (/8)</li>
      <li>Gateway: 20.20.20.20</li>
      <li>Role: Remote User</li>
      <li>Purpose: Access internal systems securely (VPN/Web/App/Voice)</li>
    </ul>
  </li>

  <li><b>Cloud</b>
    <ul>
      <li>IP Address: 20.20.20.2 / 30.30.30.2</li>
      <li>Subnet Mask: 255.255.255.252 (/30)</li>
      <li>Gateway: 20.20.20.1 / 30.30.30.1</li>
      <li>Role: External Cloud Server</li>
      <li>Purpose: Provides hosted services (VoIP trunk, backup, DNS, cloud apps, etc.)</li>
    </ul>
  </li>
</ul>

<h3>External User & Cloud Diagram</h3>



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





