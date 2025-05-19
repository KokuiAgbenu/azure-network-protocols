<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyser)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create two virtual machines using Azure one Windows machine and one Linux machine ensuring they're on the same virtual network.
- Step 2: Within the Windows VM install Wireshark protocol analyser
- Step 3: Observe initial packet capture in Wireshark
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/NlcL0A3.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating two virtual machines using Azure, use Remote Desktop or Bastion to get into the Windows VM and begin downloading Wireshark protocol analyzer within the Windows VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/iFgG5ax.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Use Wireshark to observe all the packet traffic within the Windows VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/X9ryWxK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DjbXUGq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter by ICMP traffic in Wireshark and ping the created Linux machine (private IP address, 10.0.0.5). Observe successful pings.
</p>
<br />

<p>
<img src="https://i.imgur.com/Kxygo1h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Linux machine firewall (network security group) to block inbound ICMP traffic and observe the unsuccessful pings from the Windows machine to the Linux machine. A perpetual ping was initiated from the Windows machine prior to the configuration of the Linux firewall to observe in real-time the change in network traffic. 
The configuration made to the Linux firewall was creating a new security rule that would block all ICMPv4 traffic and ensure that the rule's priority was evaluated first. 
</p>
<br />

<p>
<img src="https://i.imgur.com/e3l67ur.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the new firewall rule has taken effect you can observe the failed ping requests from the Windows VM to the Linux VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/BJ3jvHW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/hqQ5Ive.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Deleting the ICMP traffic deny rule allows the pings from the Windows VM to the Linux VM to once again become successful.
</p>
<br />

<h3>The rest of this lab is observing different types of network traffic, namely SSH, DHCP, DNS, and RDP.</h3>

<h3> SSH </h3>
<p>
<img src="https://i.imgur.com/9OTHq2V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QunSewP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filtering by SSH traffic in Wireshark and using SSH to connect to the Linux VM from the Windows VM. Observe the encrypted packets being transmitted securely over the SSH tunnel.
</p>
<br />

<h3> DHCP </h3>

<p>
<img src="https://i.imgur.com/l7y8qKr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filtering in Wireshark by DHCP traffic. Using PowerShell to release (ipconfig /release) and renew (ipconfig /renew) the Windows machine private IP address using the command. A short '.bat' file was created with the two commands and then executed in PowerShell. Observe the release, discover, offer, request, and acknowledge packets in Wireshark.
</p>
<br />

<h3> DNS </h3>

<p>
<img src="https://i.imgur.com/GhaVMdJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter network traffic by DHCP and use the nslookup command to observe DHCP network traffic.  
</p>
<br />

<h3> RDP </h3>

<p>
<img src="https://i.imgur.com/6A8Fr1w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter network traffic by RDP and observe the constant flow of RDP traffic. This is due to the live RDP connection into the Windows VM.
</p>
<br />
