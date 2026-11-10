# Practical: Wireshark ICMP Packet Analysis

## Aim
Capture and analyze ICMP Echo Request and Echo Reply packets between Kali and Metasploitable2.

## Addresses observed
- Kali: `192.168.56.103`
- Metasploitable2: `192.168.56.101`

## Procedure
1. Open Wireshark in Kali.
2. Select interface `eth0` and start capture.
3. Run `ping -c 4 192.168.56.101` in a terminal.
4. Stop capture and apply display filter `icmp`.
5. Select the matching request and reply.
6. Expand IPv4 and ICMP details.
7. Save the capture as `.pcapng`.

## Packet 5 – Echo Request
The supplied screenshot shows source `192.168.56.103`, destination `192.168.56.101`, ICMP type 8 (Echo Request), code 0 and sequence number 1. Wireshark identifies frame 6 as the response. Kali is asking the target to reply.

## Packet 6 – Echo Reply
The supplied screenshot shows source `192.168.56.101`, destination `192.168.56.103`, ICMP type 0 (Echo Reply), code 0, request frame 5 and response time about 1.006 ms. The target is replying to Kali.

| Field | Packet 5 | Packet 6 |
|---|---|---|
| Direction | Kali → target | Target → Kali |
| Source | 192.168.56.103 | 192.168.56.101 |
| Destination | 192.168.56.101 | 192.168.56.103 |
| ICMP type | 8 – Echo Request | 0 – Echo Reply |

## Conclusion
The capture shows a successful ICMP request/reply exchange between the two lab VMs.
