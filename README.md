# claude-cc-skill-security-review-skill

A Claude Code skill for reviewing application changes for security risks, especially around authentication, user input, secrets, APIs, payments, and sensitive data.

## Overview

Security review should be part of implementation, not an afterthought. This skill provides a structured checklist for reviewing code that handles identities, permissions, untrusted input, credentials, external integrations, and high-impact operations.

## When to Use It

Use this skill when:

- Adding authentication or authorization.
- Handling user input or file uploads.
- Creating API endpoints.
- Working with secrets or credentials.
- Implementing payments or sensitive features.
- Storing or transmitting private data.
- Integrating third-party services.
- Reviewing a change before release.

## Main Review Areas

### Secrets Management

- Keep secrets out of source control.
- Use environment variables or a secrets manager.
- Rotate exposed credentials.
- Avoid logging tokens and private keys.

### Authentication and Authorization

- Verify identity at the correct boundary.
- Enforce permissions server-side.
- Check resource ownership.
- Protect session and token lifecycle.
- Test denied-access paths.

### Input Validation

- Validate data at trust boundaries.
- Constrain types, sizes, and formats.
- Use safe database query patterns.
- Escape or encode output appropriately.
- Treat uploaded files and external responses as untrusted.

### API and Data Security

- Protect sensitive fields.
- Apply rate limits.
- Handle errors without leaking internals.
- Use secure transport.
- Validate webhooks and external callbacks.

### Payments and High-Impact Actions

- Validate amounts and recipients.
- Prevent duplicate operations.
- Verify transaction state.
- Require approval for irreversible actions.
- Keep audit records.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-cc-skill-security-review-skill.git ~/.claude/skills/cc-skill-security-review
```

## Usage

Invoke the skill when implementing or reviewing security-sensitive code:

```text
/cc-skill-security-review
```

Provide the affected code, intended behavior, trust boundaries, and any relevant deployment or compliance constraints.

## Recommended Review Workflow

1. Identify sensitive data and trust boundaries.
2. Inspect authentication and authorization.
3. Trace user-controlled input.
4. Review database, file, and network operations.
5. Check secrets and configuration handling.
6. Inspect error and logging behavior.
7. Review dependencies and external integrations.
8. Add tests for security-sensitive paths.
9. Document findings and recommended fixes.
10. Verify the changes before release.

## Security Checklist

- No hard-coded secrets.
- Least-privilege access.
- Server-side authorization.
- Input validation.
- Safe output handling.
- Protected sensitive data.
- Bounded resource usage.
- Secure error handling.
- Auditability for high-impact operations.
- Tests for denied and failure paths.

## Repository Contents

- `SKILL.md`: Main security review workflow and checklist.
- `README.md`: Review areas, installation, and validation guidance.

## Practical Principle

A security checklist is useful only when applied to the actual code path. Verify how data enters, moves through, and leaves the system rather than relying on generic assurances.
