# Cybersecurity Lab Setup Report
## ApexPlanet Internship – Task 1: Foundation & Environment Setup
**Student:** Adithya K R  
**Organization:** ApexPlanet Software Pvt. Ltd.

## 1. Introduction
Cybersecurity protects computers, networks, applications and data from unauthorized access, misuse, disruption and damage. A controlled virtual lab provides a safe environment for learning system administration and network analysis.

## 2. Objectives
- Understand cybersecurity fundamentals and the CIA Triad.
- Identify common cyber threats and attack vectors.
- Configure an isolated VirtualBox lab.
- Set up Kali Linux and Metasploitable2.
- Verify network connectivity.
- Perform authorized service discovery with Nmap.
- Capture and analyze ICMP packets with Wireshark.

## 3. CIA Triad
- **Confidentiality:** Information is accessible only to authorized users.
- **Integrity:** Information remains accurate and is not changed without authorization.
- **Availability:** Systems and data are accessible when needed.

## 4. Cyber threats
Malware includes viruses, worms, Trojans, ransomware and spyware. Other common threats include phishing, password attacks, denial of service, man-in-the-middle attacks, insider threats and social engineering.

## 5. Attack vectors
Common paths include exposed network services, weak or reused passwords, phishing links and attachments, unpatched software, misconfiguration, removable media, third-party dependencies and physical access.

## 6. Requirements
**Hardware:** A computer with sufficient memory, storage and processor capacity to run the virtual machines. Add your actual laptop specifications here.  
**Software:** Oracle VirtualBox, Kali Linux, Metasploitable2, Nmap and Wireshark.

## 7. VirtualBox setup
Install VirtualBox from the official Oracle website, open VirtualBox Manager, import or create the required virtual machines, and verify their memory, processor and storage settings before starting them.

## 8. Kali Linux setup
Start Kali Linux, sign in using the configured account, open a terminal and check the interface address:
```bash
ip addr
```
The lab screenshot showed `eth0` with `192.168.56.103/24`.

## 9. Metasploitable2 setup
Import the Metasploitable2 VM. In VirtualBox Settings → Network, enable Adapter 1 and set **Attached to** to **Host-only Adapter**. Select the VirtualBox Host-Only Ethernet Adapter. Start the VM and use the lab-provided login. Keep this deliberately vulnerable VM isolated.

## 10. Host-Only network
Host-Only networking lets the host and selected VMs communicate through a private virtual network. Addresses observed in the lab were Kali `192.168.56.103` and Metasploitable2 `192.168.56.101`. Confirm current addresses with `ip addr` and `ifconfig`.

## 11. Linux fundamentals
Linux is an operating system used on servers, workstations and security tools. Common commands include `pwd` (current directory), `ls -la` (list files), `cd` (change directory), `whoami` (current user), `ip addr` (network addresses) and `ps aux` (process list).

## 12. Networking fundamentals
An IP address identifies a network interface. A subnet prefix defines the network portion. A MAC address is used at the link layer. TCP is connection-oriented; UDP is connectionless; ICMP supports diagnostics; DNS resolves names; DHCP assigns network configuration; and ports identify application endpoints.

## 13. Connectivity test
From Kali, the lab used:
```bash
ping -c 4 192.168.56.101
```
An initial attempt returned `Destination Host Unreachable`. After correcting the network setup, a later attempt received four replies with 0% packet loss. This confirms connectivity at the time of the successful test.

## 14. Nmap service discovery
Nmap is used for network discovery and security auditing. The lab command was:
```bash
nmap -sV 192.168.56.101
```
The screenshot showed one host up and multiple open TCP services, including web, file-sharing, remote-login, FTP, database, VNC and Tomcat-related services. Exact results may vary.

## 15. Wireshark packet analysis
Wireshark captures and inspects network traffic. Select `eth0`, start capture, generate traffic using the ping command, stop capture and apply the display filter `icmp`. Inspect the IPv4 and ICMP sections, then save the capture as `.pcapng`.

### Packet 5 – Echo Request
The supplied screenshot shows source `192.168.56.103`, destination `192.168.56.101`, ICMP type 8 (Echo Request), code 0 and sequence number 1. Wireshark identifies frame 6 as the response. This is Kali asking the target to reply.

### Packet 6 – Echo Reply
The supplied screenshot shows source `192.168.56.101`, destination `192.168.56.103`, ICMP type 0 (Echo Reply), code 0, request frame 5 and response time about 1.006 ms. This is the target replying to Kali.

| Field | Packet 5 | Packet 6 |
|---|---|---|
| Direction | Kali → Target | Target → Kali |
| Source | 192.168.56.103 | 192.168.56.101 |
| Destination | 192.168.56.101 | 192.168.56.103 |
| ICMP type | 8 – Echo Request | 0 – Echo Reply |

## 16. Cryptography and OpenSSL
Encryption converts plaintext into ciphertext; decryption restores it using the required key. Symmetric cryptography uses one shared secret key. Asymmetric cryptography uses a public/private key pair. Hashing produces a fixed-length digest and is not reversible encryption. Digital signatures help verify authenticity and integrity. OpenSSL is a toolkit for cryptographic operations and certificate handling. Check its availability with `openssl version`. Only claim practical completion if you performed it and saved evidence.

## 17. Results and learning outcomes
The lab used Kali Linux and Metasploitable2 on a Host-Only network. Connectivity was verified using ping. Nmap was used to inspect target services, and Wireshark captured and displayed the ICMP Echo Request and Echo Reply.

## 18. Conclusion
Task 1 provided practical experience with virtual lab setup, network isolation, Linux commands, connectivity testing, service discovery and packet-level analysis. Continue all security testing only in authorized environments.

## 19. Evidence to attach
Add genuine screenshots of VirtualBox, both VMs, Host-Only settings, IP configuration, successful ping, Nmap output, Wireshark packet list, Packet 5 and Packet 6. Include the capture file only if the assignment permits it.

## 20. References
- Kali documentation: https://www.kali.org/docs/
- VirtualBox manual: https://www.virtualbox.org/manual/
- Nmap reference: https://nmap.org/book/man.html
- Wireshark documentation: https://www.wireshark.org/docs/
- OpenSSL documentation: https://docs.openssl.org/
