# HTTP Stream Analysis

## Objective
Analyze the complete HTTP conversation between
client and server using Wireshark Follow HTTP Stream.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: tcp.stream eq 28
Interface: Wi-Fi
OS: Windows

## HTTP Request Observed
Method: GET / HTTP/1.1
Host: httpforever.com
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: ********************
Accept: text/html application/xhtml+xml application/xml
Accept-Encoding: gzip deflate
Accept-Language: en-US en q=0.9

## HTTP Response Observed
Response: HTTP/1.1 200 OK
Server: nginx/1.18.0 Ubuntu
Date: Tue 09 Jun 2026 09:21:25 GMT
Content-Type: text/html
Transfer-Encoding: chunked
Connection: keep-alive
Content-Encoding: gzip
HTML Title: HTTP Forever

## Security Headers Observed
Referrer-Policy: strict-origin-when-cross-origin
X-Content-Type-Options: nosniff
Feature-Policy: accelerometer none camera none
geolocation none gyroscope none microphone none
Content-Security-Policy: default-src self

## Stream Details
Total packets: 448
Client packets: 4
Server packets: 4
Total turns: 7
Conversation size: 29 KB

## Key Observations
Complete HTTP conversation visible in plain text.
Full request headers including browser details exposed.
Server software and version nginx/1.18.0 clearly visible.
Server operating system Ubuntu clearly identified.
Full HTML source code of website visible.
All headers transmitted without any encryption.
Browser type version and operating system fully exposed.
Date and time of request clearly visible.

## Risk Assessment
Complete data exposure risk is Critical.
Server information disclosure risk is High.
Browser fingerprinting risk is High.
Man in the middle attack risk is High.

## Recommendation
Always use HTTPS instead of HTTP.
Never submit sensitive data on HTTP websites.
Use HTTPS Strict Transport Security header.
Upgrade all HTTP connections to HTTPS immediately.