# Networking Basics

- **IP address:** Identifies a network interface at the network layer.
- **Subnet/prefix:** Defines the network portion of an address. `/24` is `255.255.255.0`.
- **MAC address:** Link-layer address used on a local network.
- **Gateway:** Router used to reach other networks.
- **TCP:** Connection-oriented transport.
- **UDP:** Connectionless transport.
- **ICMP:** Diagnostic and error messages; ping uses Echo messages.
- **DNS:** Resolves domain names to IP addresses.
- **DHCP:** Dynamically assigns network configuration.
- **Port:** Identifies an application endpoint.

## Host-Only network
VirtualBox Host-Only networking connects the host and selected VMs through a private virtual network.

## Addresses observed in this lab
- Kali Linux: `192.168.56.103`
- Metasploitable2: `192.168.56.101`

## Commands
```bash
ip addr
ip route
ping -c 4 192.168.56.101
ss -tuln
```
