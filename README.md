# Different-nmap-scans-
This repository documents hands-on network scanning experiments conducted using **Nmap** on Kali Linux against an Ubuntu virtual machine (`192.168.56.10`). Each scan section covers the syntax, purpose, and visual confirmation from the terminal output.

## OS Scan
Analyzes low-level TCP/IP stack behavior (packet flags, window sizes, TTL values) to determine the operating system running on the target machine.
``` bash
nmap -O 192.168.56.10
```
<img width="1796" height="760" alt="Screenshot 2026-08-13 200336" src="https://github.com/user-attachments/assets/354eee9f-0939-4f67-800f-a17dcada5e7a" />



## Version Scan
Interrogates open ports to determine the exact software name and version number running on each service.
```bash
nmap -sV 192.168.56.10
```
<img width="1919" height="888" alt="Screenshot 2026-08-16 221219" src="https://github.com/user-attachments/assets/fa6e2f69-8f4f-4d8b-962e-4c2174549c15" />



## Ping no port scan
Performs a host discovery scan without probing individual TCP/UDP ports. It determines whether the target IP address is live on the network using ARP/ICMP packets.
```bash
nmap -sn 192.168.56.10
```
<img width="1919" height="891" alt="Screenshot 2026-08-16 223041" src="https://github.com/user-attachments/assets/da31da75-b88b-4122-ba60-4334bf6da91d" />



## Aggressive scan 
Enables a comprehensive, high-detail scan combining OS detection, service version detection, default script scanning, and traceroute into a single command.
```bash
nmap -A 192.168.56.10
```
<img width="1919" height="897" alt="Screenshot 2026-08-16 223612" src="https://github.com/user-attachments/assets/b3b4ebac-4a28-47cd-8cb9-48e58614ad0e" />



## Default script scan 
Executes Nmap's default category of safe Nmap Scripting Engine (NSE) scripts against detected open ports to collect standard metadata, such as HTTP page titles and SSH host keys.
```bash
nmap -sC 192.168.56.10
```
<img width="1919" height="897" alt="Screenshot 2026-08-17 094408" src="https://github.com/user-attachments/assets/db52cc61-03e0-45ad-a7e5-c56d2708152c" />



## Top ports scan 
Limits the scan to a specific number of the most commonly targeted ports on the internet. Scanning only the top 20 ports significantly reduces scan time while targeting high-risk services.
```bash
nmap --top-ports 20 192.168.56.10
```
<img width="1919" height="895" alt="Screenshot 2026-08-17 110928" src="https://github.com/user-attachments/assets/80299bef-6df6-431e-bd22-b951eb1c705b" />



## OS guess scan 
Forces Nmap to aggressively analyze TCP responses and output weighted percentage estimates for the target OS, even when the fingerprint signature does not yield an exact match.
```bash
nmap -O --osscan-guess 192.168.56.10
```
<img width="1919" height="883" alt="Screenshot 2026-08-17 222618" src="https://github.com/user-attachments/assets/abb53213-774d-4b2c-a0e6-3028b1883963" />



## Script scan 
Runs a targeted set of NSE scripts—in this case, the vuln category—to check open ports on the target host for known, documented vulnerabilities.
```bash
nmap --script vuln 192.168.56.10
```
<img width="1902" height="887" alt="Screenshot 2026-08-18 174844" src="https://github.com/user-attachments/assets/ebcb6867-c048-4322-8683-bc9f8b4efb2d" />



## Timing template scan 
Adjusts Nmap's timing policies to speed up packet transmission, reducing probe timeouts and accelerating scan duration on fast local networks.
```bash
nmap -T3 192.168.56.10
```
<img width="1919" height="914" alt="Screenshot 2026-08-18 221424" src="https://github.com/user-attachments/assets/1b36b486-be3a-4f6b-8291-120dd6300f19" />



## Input list scan
Reads target IP addresses line-by-line from a text file (target.txt) rather than specifying individual IP addresses manually on the command line.
```bash
nmap -iL target.txt
```
<img width="1919" height="920" alt="Screenshot 2026-08-20 225735" src="https://github.com/user-attachments/assets/256ec7c7-296e-478f-8919-7a147c80dc19" />




