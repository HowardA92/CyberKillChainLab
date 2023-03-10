<h1>Cyber Kill Chain Lab</h1>

<h2>Description</h2>
In this lab, we're going to practice hacking into a target server using Linux.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 


<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Lab walk-through:</h2>

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
We can scan it by running "nmap 10.10.164.229" at the terminal prompt.
<br />
 We just discovered three services running; FTP server, SSH server, and HTTP.
 <br />
 You can also notice that Nmap reports on whether the host is up based on whether it receives any response from it. This is useful to know when no ports are open or accessible.<br/>
<img src="https://i.imgur.com/oQ4187R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's gather more information about the FTP server.
<br />
 1. We will connect to the target FTP server by typing "ftp 10.10.164.229"<br/>
<img src="https://i.imgur.com/aRwqqEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
2. Next, we will try to log in using the login "anonymous" to see if this FTP server supports anonymous logins.  <br/>
<img src="https://i.imgur.com/WjXOhgc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3. We try to see the files available using the command "ls".  <br/>
<img src="https://i.imgur.com/u3LO9du.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4. We're going to download the file secret.txt by using the command "get secret.txt".  <br/>
<img src="https://i.imgur.com/UKjL4el.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once you download the files, type "exit" to quit the FTP client.  <br/>
<img src="https://i.imgur.com/AhW35JP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, we're going to display the contents of the file "secret.txt" using the command "cat secret.txt". We kept the password hidden so you can try it for yourself on tryhackme.com  <br/>
<img src="https://i.imgur.com/dymNmhR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
It must be the password of one of the accounts unintentionally copied to a public FTP server. Let's try it to see if it works with the root account. At the terminal, we type "ssh root@10.10.164.229". We will be asked for the password, so let's try the password we discovered in the FTP server.
 You now have complete control over the target server. <br/>
<img src="https://i.imgur.com/JzUk6Jh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's collect a couple of flags. After logging in as root, we used the following Linux commands:
 1. "pwd" to see where we are in the system. We are in the /root directory.<br/>
<img src="https://i.imgur.com/M8vUPEy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
2. "ls" to list the files.   <br/>
<img src="https://i.imgur.com/jGmz9hn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3. Use "cat flag.txt" to reveal the contents of the file. The contents were redacted so you can reveal the answer on your own. <br/>
<img src="https://i.imgur.com/4hvE4zC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Because we're logged in as root, we have full access to all files, including other users' files. 
<br />
Execute the following Linux commands:
<br />
 1. "cd /home" to go to the directory containing all the users' home directories. 
 <br />
 2. Run "ls" whiile in /home. 3. "cd librarian" to go to the user's directory. 
 <br />
 4. "pwd" to confirm that we are at /home/librarian. 
 <br />
 5. "ls" shows that librarian has a single file flag.txt. 
 <br />
 6. Print the text file contents using "cat flag.txt". The contents were redacted so you can try the lab on your own.<br/>
<img src="https://i.imgur.com/vDKvDym.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 Let's summarize what we have done in this task to get root access on the target system of IP address 10.10.164.229.
 <br />
 1. We used "nmap" to learn about the running servies.
 <br />
 2. We connected to the FTP server to learn more about its configuration.
 <br />
 3. We discovered a file containing the root password mistakenly copied to a public folder. 
 <br />
 4. We used the password we found, allowing us to log in successfully.
 <br />
 5. We gained access to all the users' files.
 .<br/>
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
