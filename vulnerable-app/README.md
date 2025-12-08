This folder contains a small demo Python app that intentionally uses vulnerable dependences to test the security scanning tool with pip-audit and SARIF conversion.

Contents:
    app.py----Simple Python script importing vulnerable packages.
    uv.lock----Lock file containing vulnerable package versions.
    README.md----Documentation of this folder.

Vulnerabilites:
    Flask 1.0
    Requests 2.22.0
    urllib3 1.22
    PyYAML 5.3
    Django 2.2.9
    These are all intentionally oudated and contain known security issues.

