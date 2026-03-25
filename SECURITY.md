# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| main (latest) | :white_check_mark: |
| Older tags | :x: |

## Reporting a Vulnerability

**Please do NOT open a public GitHub issue for security vulnerabilities.**

Instead, report security issues via:

1. **GitHub Private Security Advisory** (preferred):
   - Go to [Security Advisories](https://github.com/AuditorSEC-Initiative/bachmach-pqc-iot-sentinel/security/advisories/new)
   - Click "New draft security advisory"
   - Provide a detailed description

2. **Email:** security@auditorsec.org  
   - Subject: `[SECURITY] bachmach-pqc-iot-sentinel - <brief title>`
   - Include: affected version, hardware model, steps to reproduce, potential impact

## Response Timeline

| Step | Target Time |
|------|-------------|
| Initial acknowledgement | 48 hours |
| Triage & severity assessment | 5 business days |
| Fix development | 14-30 days (severity dependent) |
| Coordinated disclosure | 90 days after report |

## IoT & Embedded Security Scope

**In scope:**
- Cryptographic implementation vulnerabilities (side-channel, timing attacks)
- ML-KEM/ML-DSA key generation or exchange weaknesses
- Firmware update mechanism vulnerabilities
- NATS JetStream authentication/authorization bypasses
- Memory safety issues (buffer overflows, use-after-free)
- Insecure default configurations

**Out of scope:**
- Physical hardware attacks (requires physical access)
- Third-party library vulnerabilities (report to upstream: liboqs, NATS)
- Social engineering

## Disclosure Policy

We follow responsible disclosure. We will:
- Acknowledge your report promptly.
- Keep you informed throughout the fix process.
- Credit you in the security advisory (unless you prefer anonymity).
- Not take legal action against good-faith security researchers.

---

*Security policy maintained by AuditorSEC Initiative. Last updated: 2025.*
