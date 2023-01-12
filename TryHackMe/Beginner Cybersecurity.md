## Contents <img src = "https://razvioverflow.github.io/images/tryhackme/logo_0.png" width = 332px> </h2>
* [Info / Topics](README.md)
* [Log - click here to see my progress](log.md)

# Intro to offensive security
For the first Module we used a program called [[GoBuster]] to brute force a website and find hidden directories on the page.

1. We started by opening the terminal
2. and ran gobuster `gobuster -u http://fakebank.com -w wordlist.txt dir`
3. It shows that there was 2 pages open in the directory
4. we went to the **/bank-transfers** page and ran a bank transfer and verified it
---
# What is Offensive Security?
Offensive security is used to break into a system you need to think Like a hacker to beat and catch a hacker. Offensive security engineers Break into systems and record vulnerabilities in networks and software.

---
# Introduction to defensive security
Defensive security consists of two major points
1. Detecting attacks
2. Prevent intrusion
---
# Areas of defensive security
### [[Security Operations Center (SOC)]]
Is a group that monitors networks and its systems to detects malicious activity 
### [[Digital Forensics and Incident Response (DFIR)]]
#### [[Threat Intelligence]]
#### [[Digital Forensics]]
#### [[Incident Response]]
#### [[Malware Analysis]]
---
#  Practical Example of Defensive Security
### [[Security Information and Event Management  (SIEM) system]]
- A system that detects unusual actions in a system such as logins at odd hours and things out of users normal patterns. 
- As well Failed logins and logins from different locations that are not normal to the user.
---
# Careers in Cyber
## Security Analyst
- The work with stakeholders and help document different issues with a system and how to best fix them
## Security Engineer
- They test and screen security measures, as well as identify and implement systems for optimal security.
## Incident Responder
- They are a high stress job that Is in the field while the attack is like they work on setting up post incident reports as well as a intendent response plan. They work on maintaining the best security practice for a client to help prevent attacks.
## Digital Forensics Examiner
- There job is collect and analyze digital evidence just as deleted items from computers or destroyed company logs.
## Malware Analyst
- They break down and reverse engineer malware to find out the cause and source of the malware and how to defend against it to help prevent it use and spread.
## Penetration Tester
- They perform security tests and analysis of a system to help find exploits and weaknesses in network or a program.
## Red Teamer
- Same as pentester but more closer to a Black hat there job is to test the company as if they were a criminal to better help find weakness in the system by using tools such as social engineering and phishing. They pressure the system to test out the companies incident response team to see how quick they can react and contain a situation. 
---
# Web Application Security
- Goes into a brief description of web applications such as email and items like google drive that are hosted online
The pros to these is that they do not need to be installed on computer of the user and can be accessed by via a browser.
- It also went it a brief intro to [[Bug Bounty]]programs that are used by companies such as google and Facebook that pay users money to help find vulnerabilities in system.

# Web Application Security Risks
## [[OWASP Top 10]]
### Identification and Authentication Failure
- This allows the attacker attacker to use programs such as [[Hydra]] to run [[Wordlists]] against the log in screen of site to brute force entry into it. As well as sites that allow users to create weak passwords or that store password and sensitive info on plain text files that are easy to locate on the system. 
### Broken Access Control
- This is a vulnerability that happens when privilege's are not set correctly on a system such as a non admin being able to do admin actions that could break a system or make data of users public or unsafe. This is also not limited to users being able to view sensitive data that is not intended for non admins in the system such as finical info or sensitive things like SSN or License numbers. 
### Injection
- This is simply a bad design that allows user into input and upload code to a site 
### Cryptographic Failures
- This happens when weak keys are used on a system it wont be a challenge for a program to bust threw them when ABC = 123 and so on. 


---
# Practical Example of Web Application Security
This section went over the use of [[ Insecure Direct Object References (IDOR)]]
- These are pretty simple they are when a site uses example
`htttp://google.com/image002` 
to show a image but if we simply change the `image002` to `image003` we can view another image if we continue to change the number can move around the system and view things possibly unreleased or not meant for out publics eye. This is bad because we could also try to use different names like `/password.txt` and try other directories to locate and exploit data.
1. In this exercise we had to locate the user that messed up the orders we did this by changing the user number till we found the correct on the reverted the changes and view the flag.  
![](https://i.imgur.com/rPTsRiU.png)
---
#  Introduction to Operating System Security
![](https://i.imgur.com/gduKXHO.png)

---
# Common Examples of OS Security

### Authentication and Weak Passwords
- This went into a brief list of the most used passwords it talks about avoiding easy keyboard combos and simple passwords such as `123456` or `qwertyuiop` things that can be guessed easy are a bad idea to protect vs a attack.
### Weak File Permissions
- not properly securing files in a network can give a attacker access to documents and files that were not meant for public view such as credit card info and SSN
### Malicious Programs
- Trojan horse can be used to Gain access into a system

---
#  Practical Example of OS Security
1. connected to OPENVPN
2. connected to the machine on tryhackme and open WSL2 
3.  connected via `ssh sammie@10.10.175.43` with password `dragon`
4. we that looked around and saw there was another user johnny
5. we used `su - johnny` to long into that account and was prompted a password using the top 21 passwords used we found that password to be `abc123`
6. once we got in we used `history` to see what he was up to we can see that he fucked up and typed the root password
7. we used `su - root` to long into the root and used password ` happyHack!NG` to get into the root user account
8. from there we ls to find the flag and rip using `cat flag.txt`
**THM{YouGotRoot}**

---
# Network Security
![](https://i.imgur.com/qCh6fZq.png)
## [[Cyber Kill Chain]]
was designed by Lockheed martin to help predict the process in which a attacker hits a system from start to stop. It uses 7 steps
1.  Recon: Recon, short for reconnaissance, refers to the step where the attacker tries to learn as much as possible about the target. Information such as the types of servers, operating system, IP addresses, names of users, and email addresses, can help the attack’s success.
2.  Weaponization: This step refers to preparing a file with a malicious component, for example, to provide the attacker with remote access.
3.  Delivery: Delivery means delivering the “weaponized” file to the target via any feasible method, such as email or USB flash memory.
4.  Exploitation: When the user opens the malicious file, their system executes the malicious component.
5.  Installation: The previous step should install the malware on the target system.
6.  Command & Control (C2): The successful installation of the malware provides the attacker with a command and control ability over the target system.
7.  Actions on Objectives: After gaining control over one target system, the attacker has achieved their objectives. One example objective is Data Exfiltration (stealing target’s data).

---
# Practical Example of Network Security
In this exmaple we use the tool [[nmap]] which is a tool that is used to scan down Ip address
1. Started with downloading and setting up OpenVPN in  Linux
2. Then connected to the host system
3.  We started by running `nmap 10.10.216.124`
![](https://i.imgur.com/FlUjqxv.png)
4. We can see there is a ftp, ssh and http server up and running
## [[ftp]] File transfer protocol - used to transfer files 
## [[SSH]] Secure shell - used to remote log into a system
## [[http]] Hypertext transfer protocol - used for the web
5. had a issue with the ls command had to turn off firewall 
![](https://i.imgur.com/JFvc3bS.png)
6. I was able to grep the `secret.txt` file and got the password
7. I then used `ssh root@targetip` and out the password to connect. Once connected I found another txt file doing ls and was able to `cat` the text file and get the flag for the box
![](https://i.imgur.com/iwAeo58.png)
8. had to cd into the home directory then into another directory to land the last flag

---
# Practical Example of Digital Forensics
1.  Started by downloading the zip file into my system
2. I extracted the zip file into my THM Directory 
3. I open up the folder and got into file and found a pdf file I ran `pdfinfo`
![](https://i.imgur.com/MqeLFz4.png)
4. I had to install `exiftool` for this next section
5. was able to get the geo info and run it in google maps `51.51442_N_, 0.08333_W_`
![](https://i.imgur.com/GfulRes.png)
51° 30' 51.90" N, 0° 5' 38.73" W. 
6. Found the model number and closed the class

---
# Security Operations
## Data Sources the list below is used by the SOC to help detect malicious behavior on a system
### [[Server logs]] 
### [[DNS activity]]
### [[Firewall logs]]
### [[DHCP logs]]

##### This section was finished by a testing using a fake fire wall the attacker was sending packets and you had to mock blocks to the ip to stop the attack.
