Vulnerable App — Demonstration Project

This folder contains an intentionally vulnerable Python application designed for demonstrating dependency vulnerability scanning using:

pip-audit

SARIF conversion

GitHub Code Scanning (Security tab)

The goal is to show how outdated or insecure dependencies appear as alerts inside GitHub’s Security > Code Scanning Alerts.

🔍 Purpose

This app is not meant to be safe.
Its main purpose is to:

Trigger pip-audit findings

Produce a SARIF report

Upload that report to the GitHub Security tab

Show how different dependencies can create vulnerabilities

Demonstrate severity levels (Low, Medium, High)

⚠️ Intentionally Vulnerable Dependencies

The requirements.txt file includes packages that are known to have CVEs.
These outdated versions are included on purpose to generate vulnerability alerts.

Current Dependency List
# Low severity
idna==2.5
certifi==2018.8.24

# Medium severity
flask==1.0
requests==2.22.0
PyYAML==5.3

# High / Critical severity
django==2.1.0
werkzeug==0.14.1


These versions were selected because they historically contained known vulnerabilities such as:

Remote code execution (RCE)

Cross-site scripting

Deserialization attacks

Insecure defaults

Denial of service

Depending on the vulnerability data available to pip-audit, some issues may appear as Medium severity even when historically more severe. (pip-audit does not always include CVSS scores.)

📝 Expected Behavior When Scanned

When running your GitHub Actions workflow, you should expect:

✅ pip-audit

Detects vulnerabilities in outdated dependencies

Outputs JSON to vulnerable-app/pip-audit.json

✅ SARIF Converter

Converts JSON → results.sarif

✅ GitHub Code Scanning

Uploads SARIF to the Security tab

Displays one alert per vulnerability found

Marks them with severity (Low/Medium/High) based on your converter logic

