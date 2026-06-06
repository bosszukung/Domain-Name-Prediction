# Security Policy

## Supported Versions

This project is actively maintained. Security updates are provided for the current version.

| Version | Status | Support |
|---------|--------|---------|
| 1.0.x | Current | :white_check_mark: Active |
| < 1.0 | Legacy | :x: No Longer Supported |

## Reporting a Vulnerability

We take security seriously. If you discover a security vulnerability in this project, please report it responsibly.

### How to Report

1. **Do NOT create a public GitHub issue** for security vulnerabilities
2. **Email the maintainer** at your earliest convenience with:
   - Description of the vulnerability
   - Steps to reproduce (if applicable)
   - Potential impact
   - Suggested fix (if available)

3. **Include relevant details:**
   - Your GitHub username
   - Contact information
   - Any proof-of-concept code

### What to Expect

- **Acknowledgment:** You'll receive a response within 48 hours
- **Assessment:** We'll evaluate the severity and impact
- **Fix Timeline:** Critical issues receive immediate attention
- **Notification:** You'll be informed when the fix is released
- **Credit:** We'll acknowledge your contribution in release notes (if desired)

## Security Considerations

### Data Security

- This project processes domain name data
- No sensitive personal information should be included in datasets
- Always use anonymized or public data sources
- Be mindful of WHOIS data collection compliance

### Code Security

- Regular dependency updates recommended
- No hardcoded credentials or sensitive information
- Input validation for any external data sources
- Use of trusted libraries and frameworks

### Usage Guidelines

- Only use this tool for legitimate domain analysis
- Respect domain owner rights and privacy
- Comply with local and international regulations
- Follow WHOIS data usage policies

## Security Best Practices

When using this project:

1. **Environment Security**
   - Use virtual environments to isolate dependencies
   - Keep Python and libraries updated
   - Review third-party libraries before use

2. **Data Handling**
   - Don't commit sensitive data to repositories
   - Use `.gitignore` to exclude sensitive files
   - Be cautious with WHOIS API rate limits

3. **Access Control**
   - Protect your API credentials
   - Use environment variables for configuration
   - Review repository access permissions

## Dependencies

All dependencies are specified in `requirements.txt`. We recommend:
- Regularly updating packages: `pip install --upgrade -r requirements.txt`
- Checking for security advisories: `pip audit`
- Using tools like `safety` for vulnerability scanning

## Vulnerability Scanning

To scan for known vulnerabilities in dependencies:

```bash
# Using safety
pip install safety
safety check

# Using pip audit
pip audit
```

## Legal Notice

This project is provided "as-is" for educational and legitimate domain analysis purposes. Users are responsible for:
- Complying with all applicable laws and regulations
- Respecting domain owner rights
- Following WHOIS data usage policies
- Ensuring ethical use of the tools and methods

## Questions?

If you have security-related questions that aren't vulnerability reports, feel free to:
- Open a general GitHub issue (not for vulnerabilities)
- Review existing security documentation
- Check the main README.md

---

**Last Updated:** June 2026
