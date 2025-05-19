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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
