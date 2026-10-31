# OWASP ZAP – Beginner Lab Guide

## Use a safe target
Practise on a local training application such as OWASP Juice Shop, or an application you own and are explicitly authorized to test. Do not scan Shoppers Stack or other public websites without written permission.

## Setup and passive scan
1. Install OWASP ZAP from the official OWASP ZAP website.
2. Start a temporary session.
3. Start your local training target.
4. Use ZAP's Manual Explore browser or configure a dedicated browser to use ZAP as its proxy.
5. Browse the local target normally.
6. Review the Alerts tab. Passive scanning analyzes observed traffic and does not intentionally attack the target.

## Active scan
Active scanning sends test requests and can change application state or create load. Use it only in a local lab or explicitly authorized scope. Start with a small scope and low scan strength.

## Review findings
For each alert, record name, risk, confidence, affected URL, evidence, and remediation. Verify findings manually; scanner alerts can be false positives. Redact secrets and personal data from screenshots.

## Evidence
Record target scope, date/time, ZAP version, scan type, alert details, and safe reproduction notes.
