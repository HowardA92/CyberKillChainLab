<h1>Cyber Kill Chain Lab</h1>

<h2>Description</h2>
In this lab, we're going to practice hacking into a target server using Linux.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 


<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Program walk-through:</h2>

<p align="center">
Start the terminal by clicking on the terminal icon shown in the image below. <br/>
<img src="https://i.imgur.com/BrHVuPR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will be writing all the commands in the terminal shown below.
 The first step of our attack is Recon; we can speed up our reconnaissance activities using different tools that gather information about the various aspects related to the target. For simplicity, we will use a single tool in this task, Nmap. Nmap is a network scanner that helps us discover running machines and any programs running on them that are visible to the outside world. The IP address of the target is 10.10.164.229. <br/>
<img src="https://i.imgur.com/0ccUEsH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We can scan it by running nmap 10.10.164.229 at the terminal prompt.
 We just discovered three services running; FTP server, SSH server, and HTTP.
 You can also notice that Nmap reports on whether the host is up based on whether it receives any response from it. This is useful to know when no ports are open or accessible.<br/>
<img src="https://i.imgur.com/oQ4187R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's gather more information about the FTP server.
 1. We will connect to the target FTP server by typing "ftp 10.10.164.229"<br/>
<img src="https://i.imgur.com/aRwqqEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
2. Next, we will try to log in using the login "anonymous" to see if this FTP server supports anonymous logins.  <br/>
<img src="https://i.imgur.com/WjXOhgc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
