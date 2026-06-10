# HTTPS and TLS Traffic Analysis

## Objective
Analyze HTTPS and TLS encrypted traffic to understand
how encryption protects data in transit.

## Scan Details
Date: 09-June-2026
Tool: Wireshark
Filter Used: tls
Interface: Wi-Fi
OS: Windows

## Protocols Observed
TLSv1.2 - Application Data
TLSv1.1 - Client Hello with SNI cloudflare-ech.com
TLSv1.1 - Alert Level Fatal Description Handshake Failure
QUIC - Initial and Handshake packets
TCP - ACK packets on port 443

## TLS Packets Observed
TLSv1.2 - Application Data 86 bytes
TLSv1.2 - Application Data 82 bytes
QUIC Initial DCID packet PKN 2 PING CRYPTO PADDING
QUIC Initial SCID 0108 packet PKN 0 ACK CRYPTO
QUIC Handshake SCID 0108
TCP 60169 to 443 ACK Seq=1 Ack=1 Win=65280 Len=1300
TLSv1 Client Hello SNI=cloudflare-ech.com 470 bytes
TLSv1 Alert Fatal Handshake Failure 61 bytes
TLSv1 Client Hello SNI=cloudflare-ech.com 470 bytes
TLSv1 Alert Fatal Handshake Failure 61 bytes
TLSv1.2 Application Data 124 bytes
TLSv1.2 Application Data 126 bytes

## Key Observations
TLS version 1.2 is the primary protocol observed.
All application data is fully encrypted.
QUIC protocol also observed alongside TLS.
Client Hello packets show SNI cloudflare-ech.com.
Handshake failure observed on TLSv1 connections.
Port 443 used for all HTTPS connections.
Data content completely unreadable unlike HTTP.
Multiple TLS versions detected in same capture.

## HTTP vs HTTPS Comparison
HTTP traffic shows complete data in plain text.
HTTPS traffic shows only encrypted application data.
HTTP uses port 80 with no protection.
HTTPS uses port 443 with TLS encryption.
HTTP server details fully visible.
HTTPS server details completely hidden.

## Risk Assessment
Data interception risk is Low due to encryption.
TLSv1 handshake failure indicates version mismatch risk is Medium.
QUIC protocol usage adds complexity risk is Low.
Outdated TLS version risk is Medium.

## Recommendation
Disable TLSv1 and use only TLSv1.2 or TLSv1.3.
Always prefer HTTPS over HTTP connections.
Monitor for TLS handshake failures on network.
Use updated browsers supporting latest TLS versions.