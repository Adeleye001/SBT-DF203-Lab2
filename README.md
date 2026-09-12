# SBT-DF203 Lab 2 - HTTP Analysis: Embedded Image Traffic

## Overview
This lab captures and analyses plaintext HTTP traffic containing an HTML page with an embedded JPEG image. The investigation demonstrates how a browser generates multiple HTTP requests, how TCP handles the transfers, and how forensic analysts can export and verify recovered objects from network captures.

## Investigator
- **Name:** Adeleye Ademiluyi Timilehin
- **Registration:** 2025/FWSD/11459
- **Course:** SBT-DF203 Basic Networking Skills for Digital Forensics
- **Lab:** Lab 2 — HTTP Analysis: Embedded Image Traffic
- **Deadline:** 10 September 2026

## Evidence Files
- **basic.pcapng** — 20 packets captured on loopback interface (lo)
- **lab_image_original.jpg** — Original source image served by Apache
- **basic_working.pcapng** — Working copy for analysis

## Evidence Hashes
| File | SHA-256 |
|---|---|
| basic.pcapng | e9234eba629f49b849b734fd87dbbd6f3ef112f7f48e31dfd796bdc4be429b5b |
| basic_working.pcapng | e9234eba629f49b849b734fd87dbbd6f3ef112f7f48e31dfd796bdc4be429b5b |
| lab_image.jpg (original) | f2287d34ca12a3a19b38f186e52c7cc1c739aa70d8affa5f84449829acba9a38 |
| lab_image.jpg (exported) | f2287d34ca12a3a19b38f186e52c7cc1c739aa70d8affa5f84449829acba9a38 |

## Tools Used
- **Apache2** - Local web server serving image.html and lab_image.jpg
- **tshark** - Traffic capture on loopback interface
- **curl** - HTTP request generation
- **ImageMagick** - Lab image creation
- **sha256sum** - Evidence integrity verification

## Key Findings
- Two TCP connections established — one per HTTP object (ports 58036 and 58044)
- Two HTTP GET requests captured: GET /image.html and GET /lab_image.jpg
- Both returned HTTP 200 OK from Apache/2.4.68
- Image exported from PCAP — SHA-256 hash matches original exactly
- Both connections closed gracefully with FIN-ACK exchanges
- Loopback interface shows MAC addresses as 00:00:00:00:00:00

## Parts Completed
- **Setup** - Folders, Apache, webpage with embedded image
- **Part A** - Web service verified on TCP port 80
- **Part B** - 20-packet PCAP captured and hashed
- **Part C** - Two TCP handshakes identified and analysed
- **Part D** - HTTP requests/responses and TCP streams reconstructed
- **Part E** - Image exported, hash verified, connection closure documented, MAC explained

## Submission Package
- PDF Report: SBT-DF203-Lab2_2025FWSD11459_AdeleyelAdemiluyi.pdf
- ZIP Package: SBT-DF203-Lab2_2025FWSD11459_AdeleyelAdemiluyi.zip

## GitHub Repository
https://github.com/Adeleye001/SBT-DF203-Lab2
