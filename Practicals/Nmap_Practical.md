# Practical: Nmap Service Discovery

## Aim
Use Nmap in an isolated, authorized lab to identify reachable TCP ports and service information.

## Target
Metasploitable2: `192.168.56.101` (address observed in the lab).

## Command
```bash
nmap -sV 192.168.56.101
```
The `-sV` option probes open ports to help identify services and versions.

## Procedure
1. Start Kali and Metasploitable2.
2. Confirm both use the same Host-Only network.
3. Verify connectivity with ping.
4. Run the command against the lab target.
5. Review port, state, service and version columns.
6. Save genuine output or screenshot.

## Observed result
The supplied scan screenshot showed one host up and multiple open TCP services, including web, RPC, SMB/NetBIOS, remote-login, FTP, database, VNC, IRC and Tomcat-related services. Exact results can vary.

## Conclusion
Nmap provided service-discovery information about the intentionally vulnerable training VM. Scan only systems you own or are authorized to test.
