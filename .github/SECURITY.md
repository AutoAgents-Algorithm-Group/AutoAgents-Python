# Security Policy

## Supported Versions

We release patches for security vulnerabilities. Currently supported versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.x.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

We take the security of AutoAgents-Python seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### Please Do NOT:

- Open a public GitHub issue
- Disclose the vulnerability publicly until it has been addressed
- Exploit the vulnerability beyond what is necessary to demonstrate it

### Please DO:

1. **Email us privately** at the project maintainer's contact (check GitHub profile or open a private security advisory)
2. **Use GitHub's Security Advisory** feature:
   - Go to the repository's Security tab
   - Click "Report a vulnerability"
   - Fill in the details

### What to Include:

Please provide as much information as possible to help us understand and resolve the issue:

- **Type of vulnerability** (e.g., code injection, arbitrary code execution, data exposure)
- **Full paths of source file(s)** related to the manifestation of the issue
- **Location of the affected source code** (tag/branch/commit or direct URL)
- **Step-by-step instructions** to reproduce the issue
- **Proof-of-concept or exploit code** (if possible)
- **Impact of the issue**, including how an attacker might exploit it
- **Any special configuration** required to reproduce the issue

### What to Expect:

- **Initial Response**: Within 48 hours
- **Progress Updates**: At least every 7 days
- **Fix Timeline**:
  - Critical: Immediate response, fix ASAP
  - High: Fix within 30 days
  - Medium: Fix within 90 days
  - Low: Fix in next regular release

## Security Update Process

1. **Vulnerability Reported**: Security issue is submitted privately
2. **Acknowledgment**: We confirm receipt within 48 hours
3. **Assessment**: We evaluate severity and impact
4. **Fix Development**: Patch is developed and tested
5. **Coordinated Disclosure**: Fix is released and vulnerability is disclosed
6. **Credit**: Reporter is credited (unless anonymity is requested)

## Security Best Practices

When using AutoAgents-Python, we recommend:

### API Security

- Store API keys securely (environment variables, not in code)
- Use HTTPS for all API communications
- Validate and sanitize all inputs
- Implement rate limiting
- Keep dependencies up to date

### Code Execution

- **Sandbox Environments**: Use LocalSandbox or E2BSandbox for code execution
- **Input Validation**: Always validate user inputs before execution
- **Permissions**: Run with minimal required permissions
- **Isolation**: Keep untrusted code execution isolated

### Browser Automation (CUA)

- **Trusted Sites Only**: Automate trusted websites
- **Credential Security**: Never hardcode credentials
- **Captcha Handling**: Use captcha solvers responsibly
- **Data Privacy**: Handle scraped data according to privacy laws

### Knowledge Base

- **Access Control**: Implement proper access controls
- **Data Encryption**: Encrypt sensitive data at rest
- **Injection Prevention**: Sanitize inputs to prevent injection attacks
- **Regular Backups**: Maintain regular backups

### Configuration

- Never commit `.env` files or secrets
- Use environment variables for sensitive data
- Regularly rotate API keys and credentials
- Review and update security configurations

## Known Security Considerations

### Current Security Features

- Environment-based configuration
- Sandboxed code execution
- Input validation
- Secure API communication

### Areas Requiring Attention

Users should be aware of:

- **Code Execution**: Agent-generated code is executed in sandboxes
- **Browser Automation**: Web automation can access sensitive data
- **API Keys**: Protect your LLM provider API keys
- **Data Storage**: Knowledge base may contain sensitive information
- **Third-party Dependencies**: Keep dependencies updated

## Disclosure Policy

- We aim to disclose vulnerabilities responsibly
- Coordination with reporters on disclosure timing
- Public disclosure after fix is available
- CVE assignment for significant vulnerabilities

## Security Hall of Fame

We appreciate the security researchers who help keep AutoAgents-Python secure:

<!-- Security researchers will be listed here after verified reports -->

*Be the first to contribute to our security!*

## Contact

For security concerns, please use:

- GitHub Security Advisories (preferred)
- Project maintainer contacts (see GitHub profiles)

For general questions, use GitHub Issues instead.

## Acknowledgments

We follow security best practices inspired by:

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Python Security Best Practices](https://python.readthedocs.io/en/stable/library/security_warnings.html)
- [CWE/SANS Top 25](https://cwe.mitre.org/top25/)
- [GitHub Security Best Practices](https://docs.github.com/en/code-security)

---

Thank you for helping keep AutoAgents-Python and our users safe!

