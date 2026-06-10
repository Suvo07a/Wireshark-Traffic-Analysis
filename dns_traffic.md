# DNS Traffic Analysis

## Objective
Analyze DNS query and response packets to understand
how domain names are resolved to IP addresses.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: dns
Interface: Wi-Fi
OS: Windows

## Packets Captured
Source IP: 10.54.xx.xx
Destination IP: 10.54.xx.xx
Protocol: DNS
Source Port: 49858
Destination Port: 53

## DNS Queries Observed
Packet 86 - Standard query A msedge.api.cdp.microsoft.com
Packet 87 - Standard query A msedge.api.cdp.microsoft.com
Packet 88 - Standard query response for msedge.api.cdp.microsoft.com
Packet 240 - Standard query A jrpc.venom.foundation
Packet 242 - Standard query HTTPS jrpc.venom.foundation
Packet 250 - Standard query response HTTPS jrpc.venom.foundation
Packet 382 - Standard query HTTPS www.bing.com
Packet 383 - Standard query A www.bing.com
Packet 384 - Standard query response for www.bing.com
Packet 663 - Standard query A watson.events.data.microsoft.com
Packet 785 - Standard query A config.edge.skype.com
Packet 786 - Standard query A config.edge.skype.com

## Domains Resolved
msedge.api.cdp.microsoft.com
jrpc.venom.foundation
www.bing.com
watson.events.data.microsoft.com
config.edge.skype.com

## Key Observations
DNS queries are sent in plain text without any encryption.
All domain lookups are visible to anyone on the network.
Both A record and HTTPS record queries observed.
Microsoft and Bing related domains frequently queried.
DNS uses UDP port 53 for all queries.
Query and response pairs clearly visible in capture.

## Risk Assessment
DNS Spoofing risk is High.
Browsing activity exposure risk is High.
DNS hijacking risk is High.
Unencrypted DNS queries risk is Medium.

## Recommendation
Use DNS over HTTPS to encrypt DNS queries.
Use trusted DNS servers like 8.8.8.8 or 1.1.1.1.
Enable DNSSEC where possible.
Monitor for unusual or suspicious DNS queries.