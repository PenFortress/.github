# Security Policy

PenFortress is a security tool that handles sensitive vulnerability data, so we hold ourselves to a high standard. We take reports about weaknesses in PenFortress itself seriously and appreciate the time researchers put into them.

## Supported Versions

PenFortress is under active development. Security fixes are applied to the latest release and to the `main` branch.

| Version        | Supported          |
| -------------- | ------------------ |
| `main`         | Yes                |
| Latest release | Yes                |
| Older releases | No, please upgrade |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues, discussions, or pull requests.**

Use one of the private channels below:

1. **GitHub Private Vulnerability Reporting (preferred).**
   Go to the **Security** tab of the affected repository and click **Report a vulnerability**.
2. **Email:** `penfortress@gmail.com`
   Put `SECURITY` at the start of the subject line.

### What to include

The more detail you give us, the faster we can act:

- A clear description of the vulnerability and its impact
- The affected component, version or commit
- Step-by-step instructions to reproduce, or a proof of concept
- Any relevant logs, screenshots or request/response samples
- Your suggested fix, if you have one
- How you would like to be credited, if at all

Please do not include real client data or real vulnerability findings in your report.

## What to Expect

| Stage                       | Target time                                |
| --------------------------- | ------------------------------------------ |
| Acknowledgement of report   | Within 3 business days                     |
| Initial assessment          | Within 7 days                              |
| Status updates              | At least every 14 days until resolved      |
| Fix and release             | Depends on severity, critical issues first |

We follow **coordinated disclosure**. We will work with you on a fix, agree on a disclosure date, and publish a security advisory once a patch is available. We ask that you give us a reasonable time to fix the issue before sharing details publicly.

## Scope

### In scope

- Authentication and session handling (login, MFA, password reset, invitations, lockout)
- Authorization flaws: broken role or permission checks, IDOR, privilege escalation
- Project isolation failures, including one client seeing another client's data
- Bypassing the bug verification and state-transition rules
- Injection (SQL, command, template), XSS, CSRF, SSRF
- Insecure handling of evidence files and report generation (malicious uploads, path traversal, malware scan bypass)
- Audit log tampering or missing log entries
- Information disclosure through emails, error messages or API responses
- Weak or missing encryption of data at rest or in transit
- Secrets exposure in the code, configuration or Docker setup
- Vulnerable dependencies with a demonstrable impact on PenFortress

### Out of scope

- Findings that need physical access to the server or an already compromised host
- Social engineering of maintainers, contributors or users
- Denial of service through brute-force traffic volume
- Missing best-practice headers or settings with no demonstrated impact
- Vulnerabilities in third-party software with no impact on PenFortress
- Issues in a deployment that ignores the documented hardening guidance
- Automated scanner output submitted without a validated, reproducible impact

## Safe Harbor

We will not pursue legal action against researchers who:

- Make a good-faith effort to follow this policy
- Test only against their own local or self-hosted instance, never against systems or data they do not own
- Avoid privacy violations, data destruction and service disruption
- Stop testing and report immediately if they come across real user data
- Give us reasonable time to respond before any public disclosure

## Hardening Your Deployment

Self-hosting means you control the security of your installation. At a minimum:

- Serve PenFortress only over HTTPS and enable HSTS
- Keep MFA enforced for all staff accounts
- Keep secrets in environment variables or a secrets manager, never in the repository
- Restrict network access to the database and storage
- Enable encrypted backups and test your restore procedure
- Keep the application, its dependencies and the host operating system up to date
- Review the system audit log regularly

## Credits

We are happy to publicly thank researchers who report valid vulnerabilities, with their permission, in our security advisories and release notes.

Thank you for helping keep PenFortress and its users safe.
