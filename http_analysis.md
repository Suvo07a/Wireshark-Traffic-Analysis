# HTTP Traffic Analysis

## Objective
Analyze unencrypted HTTP traffic to understand how
data is transmitted over the web without encryption.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: http
Interface: Wi-Fi
OS: Windows

## Websites Visited
http://example.com
http://httpforever.com
http://http.badssl.com

## Packets Captured
Source IP: 10.xx.xx.xx
Destination IP: 146.xx.xx.xx
Protocol: HTTP
Port: 80

Packets observed:
Packet 439 - GET / HTTP/1.1
Packet 448 - HTTP/1.1 200 OK (text/html)
Packet 452 - GET /js/init.min.js HTTP/1.1
Packet 492 - HTTP/1.1 200 OK (application/javascript)
Packet 578 - GET /css/style.min.css HTTP/1.1
Packet 579 - GET /css/style-wide.min.css HTTP/1.1
Packet 580 - GET /css/style-normal.min.css HTTP/1.1
Packet 586 - GET /css/style-narrow.min.css HTTP/1.1
Packet 716 - GET /css/images/banner.svg HTTP/1.1
Packet 718 - GET /css/images/header-major-on-dark.svg HTTP/1.1
Packet 719 - GET /favicon.ico HTTP/1.1

## Protocol Details
Transmission Control Protocol observed.
Source Port: 56738
Destination Port: 80
Connection Type: HTTP/1.1

## Key Observations
HTTP traffic is completely unencrypted.
All GET requests are visible in plain text.
Server responses including file names are visible.
CSS, JavaScript and image files are all exposed.
Anyone on the same network can intercept this data.
Destination port 80 confirms unencrypted HTTP connection.

## Risk Assessment
Data interception risk is High.
Password exposure risk is High.
File and resource names fully visible risk is Medium.
Browsing activity fully visible risk is High.

## Recommendation
Always use HTTPS websites instead of HTTP.
Never enter passwords on HTTP sites.
Use a VPN on public or shared networks.
Check for padlock in browser before entering any data.