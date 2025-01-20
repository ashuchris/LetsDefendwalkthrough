<p align="center">
<img src="https://i.imgur.com/bzkYTxJ.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> SOC138 - Detected Suspicious Xls File - EventID: 77 </h1>

<h2>Tutorial Walkthrough</h2>

<p>
 In the investigation channel let's create the case by clicking on the icon as shown bellow. 
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

<p>
 Scroll down to the Network Analysis section and we see the Cs address 177.53.143.89 and its location is in Brazil. Answer the playbook accordingly.
</p>
<p>
<img src="https://i.imgur.com/etTal4F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2>Check If Someone Requested the C2</h2>
<p>
 To do this we have to go to the Log management page, make sure we switch from Pro to Basic, and paste in the malicious C2 address. We see a familiar IP address which is Sofia (the PC we are investigating) and we see a new IP address 172.16.17.24 communicating with the C2 address. This answers the playbook question.
</p>
<p>
<img src="https://i.imgur.com/F8bDXlY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2>Containment</h2>
<p>
 To contain this other infected PC we go to "Endpoint Security" page and search for the other IP address communicating with the C2 and we find that Nolan has been compromised and we contain the PC. Make sure to write your report and finish the playbook.
</p>
<p>
<img src="https://i.imgur.com/WFGdG3W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/6BbJU3M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>THE END</h2>
