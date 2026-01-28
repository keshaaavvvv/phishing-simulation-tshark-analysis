🎯 PHISHING CLICK DETECTION – TSHARK NETWORK ANALYSIS PROJECT

📸 APPLICATION / LAB PREVIEW

Phishing Page Simulation

A locally hosted phishing-style verification page used to simulate user interaction in a controlled lab environment.
<img width="1920" height="1020" alt="2026-01-27 (10)" src="https://github.com/user-attachments/assets/802cb37b-ea0c-4ea0-b11b-fd889b76feaf" />

Network Traffic Analysis

HTTP traffic captured and analyzed using TShark, showing repeated access to the phishing resource after a user click.
<img width="1718" height="849" alt="Screenshot From 2026-01-26 17-07-57" src="https://github.com/user-attachments/assets/6a5049b0-e5d6-45a4-985f-be38c8cff243" />

🎯 PROJECT OVERVIEW

This project demonstrates a controlled phishing simulation and post-click network traffic analysis using TShark.
The goal was to understand how phishing activity appears at the network level, similar to how a SOC analyst investigates incidents after a user clicks a malicious link.

The project focuses on:

1.Simulating a phishing scenario
2.Capturing HTTP traffic generated after user interaction
3.Analyzing packet-level evidence
4.Documenting findings clearly and professionally

🧪 LAB ENVIRONMENT SETUP

1-Component	Description
2-Attacker / Analyzer	Kali Linux
3-Phishing Server	Ubuntu (local HTTP server)
4-Victim Machine	Windows 10
5-Network Type	Host-only isolated virtual network

⚠️ All activity was performed in a private lab using RFC1918 IP addresses.

🛠️ TOOLS & TECHNOLOGIES USED

1-TShark – Packet capture and traffic filtering
2-Wireshark – PCAP validation (optional)
3-Linux Networking – Interface monitoring
4-Virtualization (VMware) – Isolated lab setup

📊 NETWORK & SECURITY CONCEPTS DEMONSTRATED

📦 Data Captured

1.HTTP request packets
2.Client → server communication
3.Response status codes (200 OK, 404 Not Found)

🔍 Traffic Analysis
1-Identification of repeated HTTP GET requests

2-Detection of phishing page access (/verify.html)

3-Correlation of source and destination systems

4-Timestamp-based activity tracking

🛡️ Security Skills

1-Phishing incident investigation

2-Network traffic filtering

3-Evidence preservation using PCAP files

🧠 TSHARK COMMANDS USED

1-Capture traffic

sudo tshark -i eth0 -w phishing_click.pcap

2-Filter HTTP traffic

tshark -r phishing_click.pcap -Y http

3-Extract phishing-related requests

tshark -r phishing_click.pcap -Y "http.request.uri contains \"verify\""

4-View IP 

tshark -r phishing_click.pcap -q -z conv,ip


📌 Packet capture required elevated privileges due to raw socket access on Linux.

🔍 KEY FINDINGS

1-Multiple HTTP GET requests to /verify.html were observed

2-Requests originated from the victim system

3-Successful server responses (HTTP 200 OK) confirmed page delivery

4-Repeated access indicated user interaction or page refresh

5-Typo-based requests (verify.htll) resulted in 404 Not Found, reinforcing real user behavior

📈 SKILL LEVEL & SCOPE (HONEST)

This is an entry-level SOC / Blue Team project designed to demonstrate:

1-Practical understanding of phishing workflows

2-Network traffic analysis fundamentals

3-Ability to extract and explain evidence

4-It is not an automated detection system or real-world corporate incident response — and it does not claim to be.

🎓 LEARNING OUTCOMES

✅ Understanding phishing beyond email headers

✅ Packet-level traffic analysis using TShark

✅ Identifying malicious user behavior via HTTP traffic


🔐 IMPORTANT NOTES

1-All IP addresses shown are private lab IPs

2-No real credentials or external systems were involved

3-Project is intended strictly for educational purposes

🚀 FUTURE IMPROVEMENTS 

1-Import PCAP into SIEM (Splunk)

2-Create detection rules for phishing patterns

3-Extend analysis to DNS and TLS traffic

🎯 Conclusion 

This project represents my hands-on learning in phishing analysis and network security.



