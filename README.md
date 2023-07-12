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
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Setup of virtual machines in Azure
- Using Wireshark to demonstrate how traffic is filtered
- Manipulating inbound access & ping results
- Logging into another computer using ssh protocol

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/JsBQeIT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After setting up both my virtual Windows 10 & Ubuntu (Linux) machines, I installed Wireshark, a traffic protocol analyzer on my virtual Windows 10 machine. Here you can see internet traffic being sent back and forth randomly in the background.
</p>
<br/>

<p>
<img src="https://i.imgur.com/RsUFpEY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i entered a filter for ICMP (Internet Control Message Protocol). As you can see there is no ICMP traffic at this time.
</p>
<br />

<p>
<img src="https://i.imgur.com/DsWKXaa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i sent a ping request to the virtual Linux computer and now we have ICMP traffic.
</p>
<br />

<p>
<img src="https://i.imgur.com/dBewNHb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now i sent a ping request to www.google.com and voila! more ICMP traffic..
</p>
<br />

<p>
<img src="https://i.imgur.com/dDasgHZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i am denying inbound ICMP traffic to the Linux computer. Let's see what happens when the Windows computer tries to ping it.
</p>
<br />

<p>
<img src="https://i.imgur.com/yeq72io.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As you can see, ICMP trafic has been rejected by the Linux computer.
</p>
<br />

<p>
<img src="https://i.imgur.com/4QeaiMA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i decided to filter SSH traffic in Wireshark so i logged into the Linux computer from the Windows computer via Powershell. Once i was able to login you can see the SSH traffic in Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/zYw8p6y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i decided to filter DHCP traffic in Wireshark so i executed command ipconfig /renew and Wireshark picked up the DHCP traffic.
</p>
<br />

<p>
<img src="https://i.imgur.com/w8ukSNp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here i decided to filter RDP (Remote Desktop Protocol) traffic in Wireshark. The feed in Wireshark is non-stop because one computer is always talking to the other and vice-versa.
</p>
<br />




