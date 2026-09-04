vuln_test_app.py

INTENTIONALLY VULNERABLE test fixture for Checkmarx One SAST scanner validation.
Do NOT deploy this. Do NOT expose it to a network. For scan-testing purposes only.

Contains:
  1. SQL Injection  - build_user_query() / get_user()
  2. Command Injection - ping_host()

Both take unsanitized input and pass it straight into a sink (SQL string
concatenation, os.system) so SAST should flag them as tainted data flows.
