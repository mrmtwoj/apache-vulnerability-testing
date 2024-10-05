# Apache HTTP Server Vulnerability Testing Tool

This repository provides a **Proof of Concept (PoC)** for testing various vulnerabilities in the Apache HTTP Server, including Filename Confusion Attacks, SSRF, Denial of Service, and others related to recent CVEs. The tool sends crafted HTTP requests to assess whether the server is vulnerable to certain types of attacks.

## Features
- Tests for multiple vulnerabilities including:
  - **CVE-2024-38472**: Apache HTTP Server on Windows UNC SSRF
  - **CVE-2024-39573**: mod_rewrite proxy handler substitution
  - **CVE-2024-38477**: Crash resulting in Denial of Service in mod_proxy
  - **CVE-2024-38476**: Exploitable backend application output causing internal redirects
  - **CVE-2024-38475**: mod_rewrite weakness with filesystem path matching
  - **CVE-2024-38474**: Weakness with encoded question marks in backreferences
  - **CVE-2024-38473**: mod_proxy proxy encoding problem
  - **CVE-2023-38709**: HTTP response splitting
- Provides an easy-to-use command-line interface for testing various endpoints.

## How It Works
The tool performs HTTP requests to potential endpoints that might be vulnerable to confusion attacks or misconfigurations. It checks for specific patterns and encodings that could lead to unauthorized access or system failures.

### Testing Targets
The tool checks for vulnerabilities on the following paths:
- **php-info.php**
- **xmlrpc.php**
- **adminer.php**
- **bin/cron.php**
- **cache/index.tpl.php**
- **cgi-bin/redir.cgi**
- Others with encoded URLs for potential bypass.

## Getting Started

### Prerequisites
- **Python 3.x** installed on your system.
- **Requests** library for Python to send HTTP requests.

You can install the required Python library using:
```bash
pip install requests
```
## Installation
Clone this repository:
```bash
git clone https://github.com/mrmtwoj/apache-vulnerability-testing.git
cd apache-vulnerability-testing
```
### Usage
To use the tool, provide the target URL you want to test:
```bash
python3 poc_vulnerability_testing.py --target http://<target-ip>
```
### For example:
```bash
python3 poc_vulnerability_testing.py --target http://192.168.1.10
```
## Command-Line Arguments
- **target**: The URL of the Apache server to test (e.g., http://example.com).
- **info**: Display tool information, such as the developer name, version, and related CVEs.
- **about**: Display information about the tool and its purpose.


