# Large Packet Traffic Analysis

## Objective
Analyze large network packets above 1000 bytes to
identify heavy data transfers happening on the network.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: frame.len > 1000
Interface: Wi-Fi
OS: Windows

## Packets Observed
Packet 10  - TCP  1354 bytes  50870 to 443 ACK
Packet 24  - TCP  1354 bytes  64167 to 443 ACK
Packet 59  - TCP  1354 bytes  52297 to 443 ACK
Packet 68  - QUIC 1292 bytes  Initial DCID ed8f869401ae31d0 PKN 1
Packet 69  - QUIC 1292 bytes  Initial DCID ed8f869401ae31d0 PKN 2
Packet 73  - TCP  1354 bytes  54524 to 443 ACK
Packet 76  - QUIC 1242 bytes  Initial SCID
Packet 77  - QUIC 1242 bytes  Handshake SCID
Packet 78  - QUIC 1292 bytes  Protected Payload KP0 DCID 01c96dd96
Packet 107 - QUIC 1242 bytes  Protected Payload KP0
Packet 108 - QUIC 1242 bytes  Protected Payload KP0
Packet 109 - QUIC 1242 bytes  Protected Payload KP0
Packet 110 - QUIC 1242 bytes  Protected Payload KP0
Packet 111 - QUIC 1242 bytes  Protected Payload KP0
Packet 113 - QUIC 1242 bytes  Protected Payload KP0
Packet 114 - QUIC 1242 bytes  Protected Payload KP0
Packet 116 - QUIC 1242 bytes  Protected Payload KP0
Packet 117 - QUIC 1242 bytes  Protected Payload KP0
Packet 119 - QUIC 1242 bytes  Protected Payload KP0

## Protocols in Large Packets
TCP packets carrying large ACK segments to port 443.
QUIC protocol carrying initial and handshake packets.
QUIC protected payload packets carrying encrypted data.

## Key Observations
Most large packets are QUIC protocol traffic.
QUIC is used by modern browsers for faster connections.
All large packets going to port 443 indicating HTTPS.
TCP large packets are ACK segments of size 1354 bytes.
QUIC protected payloads show encrypted data transfer.
Large packet count indicates active data downloading.
All traffic directed to secure port 443.

## Risk Assessment
Large packet flood attack risk is Medium.
Data exfiltration via large packets risk is Medium.
Normal large data transfer risk is Low.
QUIC protocol bypassing firewall risk is Medium.

## Recommendation
Monitor for unusual spikes in large packet traffic.
Implement firewall rules to control QUIC traffic.
Set packet size limits on network if required.
Regularly review large packet transfers on network.
Use intrusion detection system to flag anomalies.