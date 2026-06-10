# ICMP Traffic Analysis

## Objective
Analyze ICMP ping packets to understand network
connectivity testing and packet behavior.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: icmp
Interface: Wi-Fi
OS: Windows

## Packets Captured
Source IP: 10.xx.xx.xx
Destination IP: 142.xx.xx.xx
Protocol: ICMP
Packet Size: 74 bytes

## ICMP Packets Observed
Packet 120 - Echo ping request  id=0x0001 seq=22/5632 ttl=128
Packet 124 - Echo ping reply    id=0x0001 seq=22/5632 ttl=112
Packet 154 - Echo ping request  id=0x0001 seq=23/5888 ttl=128
Packet 157 - Echo ping reply    id=0x0001 seq=23/5888 ttl=112
Packet 201 - Echo ping request  id=0x0001 seq=24/6144 ttl=128
Packet 204 - Echo ping reply    id=0x0001 seq=24/6144 ttl=112
Packet 207 - Echo ping request  id=0x0001 seq=25/6400 ttl=128
Packet 208 - Echo ping reply    id=0x0001 seq=25/6400 ttl=112

## Key Observations
All ping requests received successful echo replies.
TTL value of 128 on requests confirms Windows machine.
TTL value of 112 on replies indicates 16 hops to destination.
Packet size is 74 bytes for all ICMP packets.
No packet loss detected in entire capture.
Sequential packet IDs confirm stable connection.
Round trip observed successfully for all 4 ping sequences.

## Risk Assessment
ICMP flood attack risk is Medium.
Network mapping via ping risk is Medium.
Normal ping traffic risk is Low.

## Recommendation
Block ICMP on public facing systems if not needed.
Monitor for ICMP flood patterns on network.
Limit ping responses on router settings.
Use firewall rules to restrict ICMP if required.