Security Scan Demo Repository

This repository demonstrates an end-to-end security scanning workflow using pip-audit, a custom SARIF converter GitHub Action, and GitHub Advanced Security Code Scanning. It contains a demo Python application with intentionally vulnerable dependencies to generate security findings.


Repository Structure

  .github/workflows/----GitHub Actions workflow YAML (main.yml)

  vulnerable-app/----Demo Python app with known vulnerable dependencies and uv.lock

  README.md----This documentation


Demo Vulnerabilities

  The vulnerable-app/ folder includes outdated and intentionally vulnerable Python packages with different severity levels:

  idna 2.5

  certifi 2018.8.24

  Flask 1.0

  Requests 2.22.0

  PyYAML 5.3

  Django 2.1.0

  werkzeug 0.14.1

  
  These versions are chosen to trigger findings when scanned by pip-audit and converted to SARIF


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
