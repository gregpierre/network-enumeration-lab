# Day 1 – Network Security Research Notes

## What Attackers Can Discover:
- Active devices on a network
- Open ports (TCP/UDP)
- Services running on ports (SSH, HTTP, FTP, etc.)
- OS information (sometimes)
- Unencrypted traffic data
- Network structure

## Tools To Explore:
- Nmap – for scanning open ports and discovering services
- Wireshark – for capturing and analyzing packets

## Questions / Thoughts:
- Can I capture my own local traffic safely?
- How do I scan a VM vs my main computer?
## Day 2 – Network Scanning and Service Enumeration

### Commands Used
nmap localhost  
nmap -sV localhost  

### Initial Scan Results
- 5000/tcp open
- 7000/tcp open

The scan completed extremely quickly because the target was localhost (127.0.0.1), meaning no external network routing was required.

### Service Version Detection (-sV)
A more detailed scan was conducted using the -sV flag to detect service versions.

Both ports (5000 and 7000) returned the following service banner:
Server: AirTunes/925.5.1

### Analysis
- Ports 5000 and 7000 are associated with Apple AirPlay (AirTunes) services.
- The services actively responded to HTTP and RTSP requests.
- The service disclosed version information (AirTunes/925.5.1).
- Version disclosure can assist attackers in identifying known vulnerabilities.
- Even legitimate services increase the system's attack surface if exposed externally.

