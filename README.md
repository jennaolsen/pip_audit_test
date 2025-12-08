Security Scan Demo Repository

This repository demonstrates an end-to-end security scanning workflow using pip-audit, a custom SARIF converter GitHub Action, and GitHub Advanced Security Code Scanning. It contains a demo Python application with intentionally vulnerable dependencies to generate security findings.

Repository Structure

  .github/workflows/----GitHub Actions workflow YAML (security-scan.yml)

  vulnerable-app/----Demo Python app with known vulnerable dependencies and uv.lock

  screenshots/----Evidence of workflow runs and Code Scanning alerts
  
  README.md----This documentation

Demo Vulnerabilities

  The vulnerable-app/ folder includes outdated and intentionally vulnerable Python packages:

  Flask 1.0

  Requests 2.19.0

  urllib3 1.24.1

  PyYAML 5.3

  Django 2.2.9

  
  These versions are chosen to trigger findings when scanned by pip-audit and converted to SARIF

Evidence of Functionality

  Screenshots showing successful workflow runs and Code Scanning alerts are provided in the screenshots/ folder:

  workflow-run.png----Actions tab showing workflow execution

  code-scanning-alerts.png----Security tab showing detected vulnerabilities

  alert-details.png----Detailed view linking findings to the code
