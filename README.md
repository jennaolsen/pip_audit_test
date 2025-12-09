🔐 Security Scan Demo Repository

This repository demonstrates an end-to-end security scanning workflow using:

pip-audit to detect vulnerable Python dependencies

A custom SARIF converter GitHub Action

GitHub Advanced Security – Code Scanning for displaying findings

It is designed as a teaching and testing project to show how dependency vulnerabilities travel from a scan → SARIF → GitHub Security Alerts.

📁 Repository Structure
/
├── .github/workflows/
│     └── main.yml            # Security scanning workflow
│
├── vulnerable-app/
│     ├── app.py              # Demo Python application
│     ├── requirements.txt    # Intentionally vulnerable dependencies
│     └── uv.lock             # Lockfile used by pip-audit
│
└── README.md                 # This documentation


The vulnerable-app/ folder contains a simple Python app whose only purpose is to generate vulnerability findings for educational use.

⚠️ Demo Vulnerabilities (Intentional)

The Python packages below are intentionally outdated so that pip-audit will detect issues.

Included Vulnerable Dependencies
Package	Version	Notes
idna	2.5	Known low-severity issues
certifi	2018.8.24	Outdated certificate bundle
Flask	1.0	Contains several moderate CVEs
Requests	2.22.0	Known medium issues
PyYAML	5.3	Historically contained RCE vulnerabilities
Django	2.1.0	Multiple high/critical CVEs in old branches
werkzeug	0.14.1	Outdated and vulnerable

These versions are explicitly chosen to produce findings when scanned, allowing you to see:

How pip-audit reports vulnerabilities

How your SARIF converter assigns severity levels

How GitHub displays them under Security → Code Scanning Alerts

🔄 How the Workflow Operates

The GitHub Actions workflow performs the following steps:

Install dependencies

Run pip-audit on the vulnerable-app folder

Produce pip-audit JSON output

Run the custom SARIF converter

Upload SARIF to GitHub Code Scanning

Display alerts inside Security → Code Scanning

This demonstrates a full round-trip from detection → transformation → reporting.


Evidence of Functionality

  The following screenshots show successful workflow runs and Code Scanning alerts. 

 <img width="1216" height="728" alt="MultipleWorkflows" src="https://github.com/user-attachments/assets/c8820c49-4bd2-4d7f-9be0-4c5739e016c0" />
 ----Actions tab showing workflow execution

 <img width="1440" height="868" alt="WorflowDetails" src="https://github.com/user-attachments/assets/ec5e7a9c-c075-4ba1-a6d4-130af0147e13" />
----Workflow Details
  

 <img width="1211" height="731" alt="CodeScanningAlerts" src="https://github.com/user-attachments/assets/997c1b67-6be7-40c6-bef8-09dba09d7164" />
 ----Security tab showing detected vulnerabilities

  <img width="1205" height="720" alt="AlertDetails" src="https://github.com/user-attachments/assets/5b486472-6dee-4aff-a571-4e13223ad94c" />
----Detailed view linking findings to the code
