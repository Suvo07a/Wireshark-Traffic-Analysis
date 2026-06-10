# ARP Traffic Analysis

## Objective
Analyze ARP packets to understand how devices
discover MAC addresses of other devices on the network.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: arp
Interface: Wi-Fi
OS: Windows

## Packets Captured
Source MAC: b2:xx:xx:xx:xx:xx
Destination: AzureWaveTec device
Protocol: ARP
Packet Size: 42 bytes

## ARP Packets Observed
Packet 71  - Who has 10.xx.xx.xx? Tell 10.xx.xx.xx
Packet 72  - 10.xx.xx.xx is at f8:xx:xx:xx
Packet 14x - Who has 10.xx.xx.xx? Tell 10.xx.xx.xx
Packet 14x - 10.xx.xx.xx is at f8:xx:xx:xx

## ARP Process Observed
Step 1 - Device sends broadcast asking who has a certain IP.
Step 2 - Target device replies with its MAC address.
Step 3 - Requesting device updates its ARP table.
Step 4 - Communication can now happen between devices.

## Key Observations
ARP requests are broadcast to entire local network.
ARP replies contain MAC address of target device.
AzureWaveTec device identified as network adapter.
ARP has no authentication mechanism built in.
All ARP communication is in plain text.
Device MAC addresses visible to entire network.

## Risk Assessment
ARP Spoofing attack risk is High.
Man in the middle attack via ARP risk is High.
MAC address exposure risk is Medium.
Normal ARP traffic risk is Low.

## Recommendation
Use Dynamic ARP Inspection on managed switches.
Implement static ARP entries for critical devices.
Monitor network for unusual ARP broadcasts.
Use network segmentation to limit ARP scope.
Enable port security on network switches.