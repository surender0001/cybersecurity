### Cybersecurity Project - Academy VM

**Objective:**
The project aims to assess the Academy Virtual Machine (VM), configure a Security Information and Event Management (SIEM) system, and perform penetration testing to identify vulnerabilities and exploit them to find the root flag.

### VM Deployment and Network Configuration:
1. **VM Setup:**
   - Download and extract the Academy VM.
   - Import it into VMware, ensuring the default network connection is set to bridged mode.
   - Log in with the provided credentials: `Username: root` and `Password: tcm`.

2. **Network Configuration:**
   - Check the network connectivity using the command `ip a`.
   - If the Ethernet connection is down, enable it using:
     ```
     ip link set dev ens33 up
     dhclient -v ens33
     ```
   - If the bridged network doesn't work, switch to NAT and retry the commands.

### SIEM Cloud Configuration:
1. **Splunk Setup:**
   - Establish an SSH connection between the Windows host and the Academy VM.
   - Download and install Splunk Universal Forwarder using `wget`.
   - Configure the forwarder to connect to Splunk Cloud and monitor logs.

### Penetration Testing:
1. **Scanning with Nmap:**
   - Use Nmap to scan for open ports on the Academy VM.
   - Identify open ports such as FTP (21/tcp), SSH (22/tcp), and HTTP (80/tcp).

2. **Exploiting FTP:**
   - Connect using anonymous FTP login and retrieve files like `note.txt`.
   - Crack any hashed passwords found using online tools.

3. **Directory Bruteforce with Gobuster:**
   - Use Gobuster to find hidden directories or files on the Academy VM.

4. **Reverse Shell:**
   - Download and modify a PHP reverse shell script to connect back to your Kali machine.
   - Upload the script to the Academy VM and execute it to gain remote access.

### Root Flag:
1. **Privilege Escalation:**
   - Use tools like Linpeas to identify potential privilege escalation vectors.
   - Modify scripts like `backup.sh` to include a reverse shell.
   - Execute the script to gain root access.

2. **Flag Retrieval:**
   - Once root access is obtained, locate and access the flag file to complete the challenge.

### Conclusion:
This project involves a comprehensive approach to cybersecurity by configuring SIEM, scanning, exploiting vulnerabilities, and escalating privileges to retrieve critical information.

