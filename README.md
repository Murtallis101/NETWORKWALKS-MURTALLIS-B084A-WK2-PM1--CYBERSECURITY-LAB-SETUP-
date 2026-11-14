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



_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ __ _ _




