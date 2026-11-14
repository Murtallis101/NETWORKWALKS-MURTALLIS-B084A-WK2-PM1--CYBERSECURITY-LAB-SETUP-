WEEK 2 | PROJECT MODULE 1
FOOTPRINTING & RECONNAISSANCE ATTACKS WITH MULTIPLE KALI TOOLS

📌 Project Overview

This repository documents the execution and findings of Week 2 - Project Module 1 (W2-PM1) focused on Footprinting & Reconnaissance Attacks using various security and information-gathering tools within Kali Linux.

The primary target of this passive and active reconnaissance module is networkwalks.com.

🛠️ Summary of Tasks Executed

Task

Tool

Purpose / Objective

Key Output / Finding

Screenshot Reference

Task 1

whois

Domain registration & WHOIS data lookup

Registrar: GoDaddy, LLC / DNS: HostGator

screenshots/task1_whois.png

Task 2

whatweb

Web technology fingerprinting

Web Server: Apache, CMS: WordPress 7.1.4

screenshots/task2_whatweb.png

Task 3

nslookup

DNS resolution to target IP address

Resolved IP: 192.232.216.135

screenshots/task3_nslookup.png

Task 4

curl -I

HTTP response header inspection

Server: Apache, Cache: x-nginx-cache

screenshots/task4_curl.png

Task 5

wafw00f

Web Application Firewall (WAF) detection

WAF Detected: ModSecurity (SpiderLabs)

screenshots/task5_wafw00f.png

Task 6

dnsrecon

Comprehensive DNS record enumeration

Found SOA, NS, MX, A, TXT, & SRV records

screenshots/task6_dnsrecon.png

🚀 Execution & Detailed Step-by-Step Findings

Task 1: Domain Registration Details (whois)

Objective: Query the public domain registration records to identify domain ownership, registration dates, contact details, and assigned name servers.

Command:

whois networkwalks.com


📷 Screenshot / Submission Proof:




Key Results & Findings:

Domain Name: NETWORKWALKS.COM

Registrar: GoDaddy.com, LLC (IANA ID: 146)

Creation Date: 2019-11-06T22:51:46Z

Expiry Date: 2027-11-06T22:51:46Z

Registrant Contact: Privacy Protected via Domains By Proxy, LLC (Tempe, Arizona, US)

Name Servers:

NS6135.HOSTGATOR.COM

NS6136.HOSTGATOR.COM

NS29.DOMAINCONTROL.COM

NS30.DOMAINCONTROL.COM

DNSSEC Status: unsigned

Task 2: Fingerprint Web Technologies (whatweb)

Objective: Identify technologies used to power the target website, including CMS version, server software, scripts, and frameworks.

Command:

whatweb networkwalks.com


📷 Screenshot / Submission Proof:


Key Results & Findings:

Target URLs Analyzed: http://networkwalks.com (301 Redirect) ➔ https://networkwalks.com/ (200 OK)

IP Address: 192.232.216.135

Web Server: Apache

Content Management System (CMS): WordPress 7.1.4

WordPress Plugin Identified: WordPress Download Manager 3.3.76

JS Libraries / Frameworks: Bootstrap [7.1.4], jQuery [3.7.1]

Analytics / Tracking: Google-Tag-Manager, Open-Graph-Protocol

Cookies Detected: __wpdm_client

Task 3: Resolve Domain to IP Address (nslookup)

Objective: Query DNS servers to translate the domain name into its corresponding IPv4 address.

Command:

nslookup networkwalks.com


📷 Screenshot / Submission Proof:


Key Results & Findings:

DNS Server Used: 10.0.0.2#53

Target Domain: networkwalks.com

Resolved IPv4 Address: 192.232.216.135

Task 4: Read HTTP Response Headers (curl -I)

Objective: Perform a HEAD request against the site to analyze raw server HTTP headers for information disclosure.

Command:

curl -I https://networkwalks.com


📷 Screenshot / Submission Proof:


Key Results & Findings:

HTTP Status Code: HTTP/2 200

Server Header: Apache

Content Type: text/html; charset=UTF-8

Cache & Proxy Headers:

x-nginx-cache: WordPress

x-endurance-cache-level: 0

Security & Policy Headers:

permissions-policy: private-state-token-redemption...

referrer-policy: no-referrer-when-downgrade

set-cookie: __wpdm_client=...; secure; HttpOnly

Task 5: Web Application Firewall (WAF) Detection (wafw00f)

Objective: Detect whether a Web Application Firewall (WAF) is active and protecting the website against payload attacks.

Command:

wafw00f networkwalks.com


📷 Screenshot / Submission Proof:


Key Results & Findings:

Target Checked: https://networkwalks.com

WAF Status: Detected

Active Protection: ModSecurity (SpiderLabs) WAF

Total Probing Requests: 2

Task 6: Comprehensive DNS Record Enumeration (dnsrecon)

Objective: Enumerate all associated DNS records including Name Servers (NS), Mail Servers (MX), Service Records (SRV), and TXT/SPF records.

Command:

dnsrecon -d networkwalks.com


📷 Screenshot / Submission Proof:


Key Results & Findings:

SOA Record: ns6135.hostgator.com (50.87.144.87)

NS Records:

ns6136.hostgator.com (192.232.216.131) - BIND v9.16.23-RH

ns6135.hostgator.com (50.87.144.87) - BIND v9.16.23-RH

A Record: networkwalks.com ➔ 192.232.216.135

MX Record: mail.networkwalks.com ➔ 192.232.216.135

TXT Records:

Google Site Verification: google-site-verification=rr04eRmqHoWY3XemnizDNVK4q75X-Ij-mjgEeg-UsYI

SPF Record: v=spf1 +a +mx +ip4:50.87.144.87 +include:websitewelcome.com ~all

SRV Records (Auto-discovery Services):

Multiple _autodiscover._tcp.networkwalks.com pointing to cpanelemaildiscovery.cpanel.net (Ports 443)

🏁 Conclusion

The reconnaissance phase successfully gathered essential infrastructure metadata for networkwalks.com. The asset operates on Apache behind a ModSecurity WAF, utilizing HostGator DNS servers and running a WordPress-based web application.

Disclaimer: This documentation and associated commands were performed for educational and authorized testing purposes as part of the Network Walks Cybersecurity Course.


_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _

WEEK 2-PROJECT MODULE 5
WEEK 2 | PROJECT MODULE 5NETWORK SCANNING WITH ZENMAP: CYBERSECURITY & ETHICAL HACKING PROJECT TASKS

Tasks
Task1
Download & install Zenmap from official website on your Windows PC
Run the setup file after download & follow as in below
Click on install

Task2
Find your local IP address & your LAN subnet
Open CMD & run ipconfig command to find your PC’s local IP address & your local LAN subnet:
CMD: ENTER ipconfig


Task3
Find the list of live hosts/PC’s in your IP subnet
 Open Zenmap, input the local LAN subnet & select Ping Scan to find the list of live hosts in your subnet: 


Task4
How many hosts are live in your subnet? 
Answer: 11 hosts are live (including my PC)


Task5
What are the IP addresses of the live hosts? 
Answer: 10.0.0.2
        10.0.0.3
 	      10.0.0.4 
        10.0.0.6
        10.0.0.7
        10.0.0.8
        10.0.0.9
        10.0.0.12
        10.0.0.13
        10.0.0.14
        10.0.0.19


Task6
What are the MAC addresses of the live hosts?

MAC Address: D0:32:C3:77:FF:06 (D-Link)
MAC Address: 64:95:6C:AE:4B:9A (LG Electronics)
MAC Address: A6:EF:5A:A5:EF:5A (Unknown)
MAC Address: 82:2F:EE:32:0B:C1 (Unknown)
MAC Address: 88:DE:39:D6:C7:EF (Hangzhou Hikvision Digital Technology)
MAC Address: 3C:4E:56:30:8C:68 (Shenzhen Chuangwei-RGB Electronics)
MAC Address: 28:C5:38:8B:62:3F (Apple)
MAC Address: 82:A7:03:19:2D:14 (Unknown)
MAC Address: A6:EF:5A:3F:59:DB (Unknown)
MAC Address: AC:E3:42:96:1E:C1 (Huawei Technologies)
MAC Address: AC:E3:42:96:1E:C1 (Huawei Technologies)



Task 7: 
Display & save the output topology in PDF Format on your desktop: 
Click on Topology, turn on legend, read the legend in detail & click on Save Graphic:



_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _

Networkwalks-WK2-Footprinting-Scanning
Hands-on passive & active web footprinting, DNS enumeration, subnet scanning, ARP interrogation, and topology mapping for Networkwalks Week 2 lab curriculum.

_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _

PENETRATION TESTING & NETWORK SCANNING REPORT
Description & Overview
This report documents the practical security analysis executed during Week 2 (W2-PM1 and W2-PM5) under the Networkwalks Cybersecurity Internship Program. All testing was executed in full compliance with explicit authorization within scoped target environments (networkwalks.com and isolated virtual lab subnets). The primary objective was to perform passive and active domain reconnaissance, gather target infrastructure metadata, discover active hosts on local subnets, analyze host routing, map network topology, and extract physical MAC identifiers via ARP table interrogation. Unapproved distribution or misuse of this technical data is strictly prohibited.

1. Document Metadata & Scope
Pentester Name: Rushna Imran (Cybersecurity Professional)
Program / Batch: Networkwalks Cybersecurity Internship
Date: November 2026
Modules Completed: W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Subnet Scanning)
Target Environments:
networkwalks.com (Secured written permission)
Local Subnet / Virtual LAN Network (192.168.56.0/24)
Permission Status: Explicit Authorized Access Granted
Phases Covered: Phase 1 (Reconnaissance & Footprinting), Phase 2 (Scanning & Network Discovery)
2. Executive Summary & Liability Disclaimer
This report covers the execution of Week 2 tasks (W2-PM1 and W2-PM5) under the Networkwalks Cybersecurity Internship Program. All activities adhered to authorized testing boundaries. The primary goal involved domain reconnaissance, infrastructure metadata gathering, subnet host discovery, and topology mapping.

3. Technical Activities & Findings
3.1 Domain Reconnaissance & Footprinting (Task W2-PM1)
Target Domain: networkwalks.com / www.networkwalks.com

WHOIS & DNSRecon Enumeration: Extracted domain registrar records identifying SOA server ns56135.hostgator.com (50.87.144.87), NS records ns56135.hostgator.com and ns56136.hostgator.com, MX mail server mail.networkwalks.com (192.232.216.135), A record 192.232.216.135, and SPF TXT policy v=spf1 +a +mx +ip4:50.87.144.87 +include:website-welcome.com ~all.
WhatWeb Fingerprinting: http://www.networkwalks.com returned HTTP 301 Moved Permanently (Apache server in US), redirecting to https://networkwalks.com/ which returned HTTP 200 OK (Apache, WordPress 7.1.4, Bootstrap 7.1.4, IP 192.232.216.135, Title: Networkwalks Academy).
WAF Inspection (wafw00f): Analyzed HTTP request/response behaviors to verify Web Application Firewall presence (ModSecurity).
DNS Resolution (nslookup): Resolved target domain via local DNS server (192.168.10.1#53), confirming non-authoritative resolution for networkwalks.com to IP 192.232.216.135.
HTTP Header Analysis (curl -I): Extracted HTTP/2 200 OK headers revealing server: Apache, x-powered-by: PHP/7.4.33, x-endurance-cache-level: 0, and permissions-policy parameters.
3.2 Subnet Discovery & Topology Mapping (Task W2-PM5)
Target Network: Local Virtual Subnet (192.168.56.0/24)

Executed Nmap host discovery (-sn) and intense scan profiles via Zenmap GUI across the target subnet.
Identified active live host (192.168.56.1) and verified open port profiles and running service banners.
Extracted physical interface hardware addresses using local ARP table interrogation (arp -a).
Rendered visual network topology diagrams using Zenmap's interactive graph visualizer and exported graphic vector files (zenmappgraphics.pdf).
4. Risk Analysis & Threat Impact
Passive Reconnaissance Information Exposure: Publicly accessible DNS, MX, and WHOIS metadata allow external attackers to map corporate web infrastructure without triggering intrusion alarms.
Internal Subnet Exposure: Open ports and unsegmented broadcast domains allow potential lateral movement once an initial network foothold is gained.
5. Security Recommendations
Implement WHOIS privacy protection on corporate domains to obscure administrative contact vectors.
Enforce internal network micro-segmentation (VLANs) and ARP inspection controls to limit lateral discovery.
Harden exposed web servers and update Web Application Firewall (WAF) filtering rulesets.
6. Conclusion
All Phase 1 and Phase 2 tasks specified in the Week 2 curriculum were successfully executed and validated. Technical evidence including CLI output logs, host IP/MAC tables, screenshot captures, and exported topology graphics have been compiled for portfolio verification.

7. Tools & Command Reference
The following table outlines all command-line tools and utilities deployed during this security assessment, detailing their specific technical purpose:

Command / Tool	Technical Purpose & Operational Context
whois networkwalks.com	Queries public domain registrars to retrieve ownership details, administrative contacts, creation dates, and authoritative name servers.
dnsrecon -d networkwalks.com	Enumerates DNS infrastructure records (A, MX, NS, SOA, TXT/SPF) to map public routing and mail handling servers.
nslookup networkwalks.com	Performs direct DNS queries to map hostnames to IP addresses and verify local DNS server responses.
whatweb www.networkwalks.com	Fingerprints target web applications, identifying web server software (Apache), CMS versions (WordPress), and backend frameworks.
wafw00f https://networkwalks.com	Probes target endpoints with crafted HTTP requests to detect Web Application Firewalls (WAF) protecting the web application.
curl -I https://networkwalks.com	Fetches HTTP response headers only to inspect web server banners, PHP runtime versions, and caching rules.
ping -c 4 8.8.8.8	Sends ICMP echo requests to verify basic network-layer connectivity and DNS reachability before executing scans.
nmap -sn 192.168.56.0/24 / Zenmap	Scans subnets to perform host discovery, port scanning, service versioning, and visual network topology generation.
arp -a	Queries the local ARP cache to map IP addresses to physical MAC hardware addresses across the network segment.
8. Evidences Collected (in the google docs PDF down below!)
Terminal log outputs (dnsrecon, nslookup, whatweb, curl -I, whois, Nmap/Zenmap).
Local ARP table mapping outputs.
Topology graphic PDF export (zenmappgraphics.pdf).
Technical troubleshooting logs (Hypervisor screen captures, DNS resolution handling).


Author & Reference Information

•	Author: Murtallis Marcus Roux

•	LinkedIn Profile: www.linkedin.com/in/murtallis-roux-02b030270

•	Github link: [github.com/Murtallis101/NETWORKWALKS-MURTALLIS-B084A-WK2-PM1--CYBERSECURITY-LAB-SETUP-/tree/main](https://github.com/Murtallis101/NETWORKWALKS-MURTALLIS-B084A-WK2-PM1--CYBERSECURITY-LAB-SETUP-/edit/main/README.md)](https://github.com/Murtallis101/NETWORKWALKS-MURTALLIS-B084A-WK2-PM1--CYBERSECURITY-LAB-SETUP-/edit/main/README.md)

•	Google Docs Report: [PENETRATION TESTING REPORT.pdf](https://github.com/user-attachments/files/34847036/PENETRATION.TESTING.REPORT.pdf)



