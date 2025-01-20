<p align="center">
<img src="https://i.imgur.com/flCs5hu.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> SOC138 - Detected Suspicious Xls File - EventID: 77 </h1>
This is a walkthrough of the resolution of this ticket<br />

<h2>Tutorial Walkthrough</h2>

<p>
 In the investigation channel lets create the case by clicking on the icon as shown bellow. 
</p>
<p>
<img src="https://i.imgur.com/qqhrrpy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 We get taken to the Case Management section. Click on Start Playbook. 
</p>
<p>
<img src="https://i.imgur.com/pkJaGzb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Check if the malware is quarantined/cleaned</h2>
<p>
 To solve this we need to go back to the Investigation Channel and look at the details of the alert. We need to take note of the specific Computer name or the IP address of the affected PC. 
</p>
<p>
<img src="https://i.imgur.com/e3Xm7xc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 We go to Endpoint Security and search for the device which is suspected to be compromised. The name is Sofia.  
</p>
<p>
<img src="https://i.imgur.com/0taCRtu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 The Malware is not quarantined. To clean it up, toggle the button to contain the host. Then go back to your playbook and answer the question accordingly.
</p>
<p>
<img src="https://i.imgur.com/e0hhBz2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h2>Analyze malware in 3rd party tools and find C2 address</h2>
<p>
 To look for C2 addresses we can use a variety of tools. Let's use hybrid analysis. Go back to the investigation channel, right-click on the suspected infected file, and copy the link path. Then paste it into hybrid analysis and click on Analyze.
</p>
<p>
<img src="https://i.imgur.com/rv1UfHH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 <p>
<img src="https://i.imgur.com/gqSbA6b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 As we can see a scan of this file results in it being flagged as Malicious which answers our playbook question.
</p>
<p>
<img src="https://i.imgur.com/Suaxxn0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
 What about the Cs addresses? To look for them, scroll down to "Relations", click on the malicious file, scroll down to "Falcon Sandbox Reports" and click on the first one to get a detailed report of the "ORDER SHEET & SPEC.xlsm" file
</p>
<p>
<img src="https://i.imgur.com/zoDFc9V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/48lRK0Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


