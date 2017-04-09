# Project 10 - Honeypot

Time spent: **3** hours spent in total

> Objective: Setup a honeypot and provide a working demonstration of its features.

### Required: Overview & Setup

- [x] A basic writeup (250-500 words) on the `README.md` desribing the overall approach, resources/tools used, findings
- [x] A specific, reproducible honeypot setup, ideally automated. There are several possibilities for this:
	- A Vagrantfile or Dockerfile which provisions the honeypot as a VM or container
	- A bash script that installs and configures the honeypot for a specific OS
	- Alternatively, **detailed** notes added to the `README.md` regarding the setup, requirements, features, etc.
---
**Setup**

For this project, I set up  a low-interaction honeypots on a telnet port (port 23) from my kali linux VM. To do this, I dowloaded and configured a saftey kit application/IDS called "PenTBox". I followed the honeypot installation guide from www.iexplo1t.com. First step was to install the pentbox-1.8 by using the wget command: wget http://downloads.sourceforge.net/project/pentbox18realised/pentbox-1.8.tar.gz. The next step is to uncompress the pentbox files by using the following command: tar -zxvf pentbox-1.8.tar.gz. Once that is done, go into pentbo-1.8 directory and run the pentbox's ruby script called: pentbox.rb. </br></br>Next part is to configure the honeypot. On the first menu screen, type "2" to select the option 2-Network tools. On the second menu, type "3" to select Honeypot. You need to select "2-Manual Configuration" In order to configure a honeypot on the telnet so type "2". Now for the configuration, type "21" to specify telnet port (port 21), insert any false message to display to the attacker, type "y" to save an intrusion log, and type "n" to deactivate the beeping sound.
---

### Required: Demonstration

- [x] A basic writeup of the attack (what offensive tools were used, what specifically was detected by the honeypot)
- [x] An example of the data captured by the honeypot (example: IDS logs including IP, request paths, alerts triggered)
- [x] A screen-cap of the attack being conducted

<img src='./honeypot.gif' title='Video Walkthrough' width='' alt='Video Walkthrough Honeypot' />
---
**Attack**

For the demonstration, I used a tool called nmap to port scan the kali linux VM with the intense flag set (nmap -T4 A -v 10.0.2.15). Sure enough the intrusions were detected and were logged. Afterwards, I tried to telnet into the Kali VM and was forced out with an alert message that I setup from the configuration.
---

### TODO: Features
- Honeypot
	- [ ] HTTPS enabled (self-signed SSL cert)
	- [ ] A web application with both authenticated and unauthenticated footprint
	- [ ] Database back-end
	- [ ] Custom exploits (example: intentionally added SQLI vulnerabilities)
	- [ ] Custom traps (example: modified version of known vulnerability to prevent full exploitation)
	- [ ] Custom IDS alert (example: email sent when footprinting detected)
	- [ ] Custom incident response (example: IDS alert triggers added firewall rule to block an IP)
- Demonstration
	- [ ] Additional attack demos/writeups
	- [ ] Captured malicious payload
	- [ ] Enhanced logging of exploit post-exploit activity (example: attacker-initiated commands captured and logged)