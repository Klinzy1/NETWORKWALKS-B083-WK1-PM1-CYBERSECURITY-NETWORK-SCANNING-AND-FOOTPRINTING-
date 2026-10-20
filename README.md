Cybersecurity & Ethical Hacking — Week 2 Project

Network Scanning (Zenmap/Nmap) & OSINT Footprinting (theHarvester)

1. Project Overview

This project explores two essential cybersecurity reconnaissance techniques: network scanning and Open-Source Intelligence (OSINT) footprinting. Zenmap/Nmap was used to discover active devices on a private home network, while theHarvester was used to gather publicly available information associated with "microsoft.com".

2. Project Objectives

- Identify live hosts on a local network.
- Examine IP addresses, MAC addresses, and vendor information.
- Understand network discovery and topology visualization.
- Use theHarvester to gather public domain-related information.
- Analyze reconnaissance results and identify defensive security practices.

3. Tools Used

- Zenmap: Graphical interface for Nmap.
- Nmap 7.991: Network host discovery.
- theHarvester: OSINT footprinting.
- Kali Linux: Cybersecurity testing environment.
- VirtualBox: Virtualization platform.

4. Network Scanning with Zenmap/Nmap

Target subnet: "10.0.4.0/22"
Scan type: Ping scan
Command:

nmap -sn 10.0.4.0/22

Results from the screenshot:

- IP addresses scanned: 1,024
- Live hosts found: 5
- Scan duration: 12.07 seconds
- Nmap version: 7.991
- Scan date: 8 October 2026

Discovered hosts:

IP Address| MAC Address| Vendor
"10.0.4.1"| "C0:6F:98:3E:3B:F2"| eero
"10.0.4.20"| "AC:41:6A:14:61:B3"| Amazon Technologies
"10.0.4.27"| "AA:D1:44:FE:7C:2D"| Unknown
"10.0.4.28"| "B4:AE:2B:1F:DA:79"| Microsoft
"10.0.4.30"| Not displayed| Not displayed

Analysis: The scan identified five responsive hosts. Four had MAC addresses displayed, and vendor identification was available for three devices. Zenmap's Topology view can also be used to visualize discovered hosts, if captured.

5. OSINT Footprinting with theHarvester

Target domain: "microsoft.com"

Task A — Baidu source

Command:

theHarvester -d microsoft.com -l 1000 -b baidu

Results:

- IP addresses: 0
- Email addresses: 0
- Hosts: 0

The zero-result output demonstrates that results depend on the selected source, indexing, and availability. It does not mean the domain has no public information.

Task B — Multiple sources

Command:

theHarvester -d microsoft.com -l 50 -b all | tee task2_output.txt

Reported results from the original project notes:

- Subdomains identified through DNS fallback: 14
- Autonomous System Numbers (ASNs): 10
- Interesting URLs: 3
- IP addresses: 139
- Email addresses: 3
- Hosts: 9,966

These figures should be checked against the original output file before being treated as verified results. Entries may overlap or require validation.

6. Key Findings

1. Nmap identified five responsive hosts within the specified private subnet.
2. MAC addresses and vendor information helped characterize some devices.
3. The Baidu-only search returned no results, while the multi-source search reportedly gathered more information.
4. OSINT results vary by source and time.
5. Discovered hosts, IP addresses, and email addresses require verification before being treated as confirmed assets.

7. Security Recommendations

- Maintain an accurate inventory of authorized network devices.
- Investigate unknown devices and verify their ownership.
- Conduct periodic authorized network scans.
- Review publicly exposed organizational information.
- Validate and deduplicate OSINT findings.
- Document commands, timestamps, tool versions, screenshots, and outputs.
- Avoid publishing sensitive home-network information.

8. Project Limitations

- A ping scan does not identify all open ports, running services, or vulnerabilities.
- Some devices may not respond to discovery probes.
- MAC vendor identification may be incomplete.
- OSINT results depend on source availability and configuration.
- The reported theHarvester results require verification.
- No exploitation or vulnerability testing was performed.

9. Skills Demonstrated

Network reconnaissance, Nmap command execution, subnet addressing, MAC-address interpretation, Zenmap visualization, OSINT footprinting, Linux command-line usage, technical documentation, and ethical cybersecurity practices.

10. Conclusion

This project provided practical experience in network discovery and OSINT footprinting. Zenmap/Nmap identified five responsive devices on a private network, while theHarvester demonstrated how publicly available sources can reveal domain-related information. The exercise reinforced the importance of responsible reconnaissance, validating results, maintaining asset visibility, and documenting security findings.

11. Supporting Evidence

- Zenmap scan screenshot.
- Zenmap Topology view, if available.
- theHarvester Baidu-source results.
- Multi-source theHarvester results.
- Saved output file: "task2_output.txt".

Disclaimer: This project was conducted for educational purposes. Network scanning was limited to the author's private home network, and OSINT activities focused on publicly available information. All testing should be performed only within an authorized scope.

Completed as part of a Week 2 Cybersecurity & Ethical Hacking internship module.