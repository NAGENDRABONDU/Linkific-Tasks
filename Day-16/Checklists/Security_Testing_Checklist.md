# Basic Security Testing Checklist

## Authentication
- [ ] Valid login succeeds; invalid login fails generically.
- [ ] Empty credentials are rejected; password is masked.
- [ ] Logout invalidates the session; reset tokens are time-limited and single-use.

## Authorization
- [ ] Protected pages reject logged-out users.
- [ ] Users cannot access another user's records by changing IDs.
- [ ] Normal users cannot invoke admin-only actions.
- [ ] Server enforces permissions.

## Input and sessions
- [ ] Server validates required fields, types, and lengths.
- [ ] SQL injection strings are treated as data.
- [ ] HTML/script input is safely encoded.
- [ ] Session cookies use appropriate Secure, HttpOnly, SameSite flags.
- [ ] Session expiry and logout are enforced.
- [ ] CSRF protection is applied where required.

## Transport and configuration
- [ ] HTTP redirects to HTTPS or is disabled.
- [ ] No mixed content on HTTPS pages.
- [ ] Errors do not expose stack traces or secrets.
- [ ] Security headers and dependencies are reviewed.
- [ ] Security logs do not record passwords or tokens.

## Scanning and reporting
- [ ] ZAP passive scan performed within approved scope.
- [ ] Active scan performed only in an authorized lab.
- [ ] Findings checked for false positives.
- [ ] Evidence is redacted and findings include impact and remediation.
