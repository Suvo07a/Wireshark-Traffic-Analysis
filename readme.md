# Wireshark Network Traffic Analysis

## Objective
This project involves capturing and analyzing different
types of network traffic using Wireshark to understand
how various protocols work and identify potential
security risks in a home network environment.

## Tools Used
Wireshark 4.x
Windows 11
Google Chrome Browser
Command Prompt CMD

## System Information
OS: Windows 11
Interface: Wi-Fi
Network Adapter: AzureWaveTec
Capture Date: 09 June 2026

## Project Structure

screenshots folder contains all wireshark capture screenshots.
analysis folder contains detailed reports for each protocol.
README.md contains full project overview and findings.

## Traffic Types Analyzed

HTTP Traffic
Captured unencrypted web traffic from httpforever.com.
Used http filter to isolate HTTP packets.
Followed HTTP Stream to see complete conversation.

HTTP Stream Analysis
Captured full request and response conversation.
Server details and HTML source code fully visible.
Proves that HTTP has zero encryption protection.

DNS Traffic
Captured DNS queries using nslookup commands.
Observed queries for microsoft.com bing.com and skype.com.
Used dns filter to isolate DNS packets.

ICMP Traffic
Captured ping packets to google.com and 8.8.8.8.
Observed Echo Request and Echo Reply packets.
Used icmp filter to isolate ICMP packets.

ARP Traffic
Captured ARP broadcast packets on local network.
Observed Who has requests and MAC address replies.
Used arp filter to isolate ARP packets.

HTTPS and TLS Traffic
Captured encrypted HTTPS traffic using tls filter.
Observed TLSv1.2 Application Data packets.
Observed QUIC protocol packets alongside TLS.
Compared with HTTP to show importance of encryption.

Large Packet Analysis
Used frame.len greater than 1000 filter.
Observed large TCP and QUIC packets on port 443.
Identified heavy data transfer patterns on network.

## Key Findings

HTTP traffic sends all data in complete plain text.
Full browser details and server information exposed on HTTP.
DNS queries are unencrypted and reveal all browsing activity.
ICMP ping packets show TTL of 128 confirming Windows machine.
ARP packets expose MAC addresses of all local devices.
HTTPS traffic is fully encrypted and data is unreadable.
QUIC protocol observed for faster encrypted connections.
Clear difference proven between HTTP and HTTPS security.

## Vulnerability Summary

HTTP unencrypted traffic risk level is Critical.
DNS plain text queries risk level is High.
ARP spoofing possibility risk level is High.
TLSv1 handshake failure risk level is Medium.
ICMP network mapping risk level is Medium.

## Recommendations

Replace all HTTP connections with HTTPS immediately.
Use DNS over HTTPS to encrypt DNS queries.
Implement Dynamic ARP Inspection on network.
Disable TLSv1 and use only TLSv1.2 or TLSv1.3.
Use a VPN on public or shared networks.
Never enter passwords on HTTP websites.
Monitor network regularly for suspicious traffic.

## What I Learned

How HTTP transmits data without any encryption.
How DNS resolves domain names to IP addresses.
How ICMP ping works and what TTL values mean.
How ARP discovers MAC addresses on local network.
How HTTPS and TLS protect data from interception.
How to use Wireshark filters effectively.
How to identify security risks from network captures.
How to document network analysis professionally.

## Disclaimer
All network captures were performed on my own personal
home network for educational purposes only.
No unauthorized systems or networks were accessed.
All IP addresses have been anonymized for privacy.
All screenshots have been reviewed and sensitive
information has been removed before publishing.