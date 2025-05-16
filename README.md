# NMAP
Utilize Nmap to perform a comprehensive port scan and vulnerability assessment on a provided IP address or network range. Document the process, including the Nmap commands used and the findings obtained
What Is Nmap?

Nmap (Network Mapper) is a free and open-source tool used for network discovery and security auditing. It helps identify live hosts, open ports, running services, and potential vulnerabilities on a network.

 Setting Up Nmap

 Installation

- Linux (Debian/Ubuntu):

  bash
  sudo apt update
  sudo apt install nmap
  

- macOS (using Homebrew):

  bash
  brew install nmap
  

- Windows:

  Download the installer from the [official Nmap website](https://nmap.org/download.html) and follow the installation prompts.


 Performing a Port Scan

To identify open ports and services on a target IP address or network range, use the following command:

bash
nmap -sS -sV -T4 192.168.1.0/24

Explanation:

- sS: Performs a TCP SYN scan (stealth scan).

- sV: Attempts to determine the version of the services running on open ports.

  -T4: Sets the timing template to speed up the scan (use with caution).

- 192.168.1.0/24: Specifies the target network range.

 Conducting a Vulnerability Assessment
Nmap includes the Nmap Scripting Engine (NSE), which allows users to write and use scripts for automated tasks, including vulnerability detection.

 Using Built-in Vulnerability Scripts

To scan for known vulnerabilities using built-in scripts:

bash
nmap --script vuln 192.168.1.100


Explanation:

- --script vuln: Runs a collection of scripts that check for various vulnerabilities.

- 192.168.1.100: Specifies the target IP address.

🔹 Using the vulners Script

The vulners script integrates with the Vulners vulnerability database to provide detailed information:

bash
nmap -sV --script vulners 192.168.1.100


Note: Ensure the vulners script is installed and updated.

---

📄 Documenting the Process

It's essential to save the scan results for analysis and record-keeping. Nmap allows output in various formats:

- Normal output:

  bash
  nmap -oN scan_results.txt 192.168.1.100
  

- XML output:

  bash
  nmap -oX scan_results.xml 192.168.1.100
  

- Grepable output:

  bash
  nmap -oG scan_results.gnmap 192.168.1.100
  

Sample Findings

After running the scans, you might discover:

- Open Ports: e.g., Port 22 (SSH), Port 80 (HTTP).

- Service Versions: e.g., Apache httpd 2.4.41.
- Potential Vulnerabilities: e.g., CVE identifiers linked to outdated services.

These findings help in assessing the security posture of the network and planning remediation steps.
