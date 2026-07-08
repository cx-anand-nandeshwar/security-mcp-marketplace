---
name: dlp-scan
description: Scan content for data loss prevention violations using the Checkmarx DLP MCP server
instructions: |
  Use this skill to detect sensitive data, secrets, and compliance violations in code and content.
  The skill connects to the Checkmarx DLP MCP server to provide real-time security scanning.
tags:
  - security
  - dlp
  - secrets-detection
  - compliance
---

This skill enables scanning for data loss prevention violations, including:
- Detection of hardcoded secrets and API keys
- Identification of sensitive data patterns (PII, financial data, etc.)
- Compliance checks for regulatory requirements
- Real-time vulnerability scanning

## Usage

Invoke this skill when you need to:
- Scan code repositories for security vulnerabilities
- Detect exposed secrets or credentials
- Check for compliance violations
- Identify sensitive data in source code

## Configuration

This skill requires the Checkmarx DLP MCP server to be configured via `.mcp.json` with:
```json
{
  "mcpServers": {
    "Checkmarx": {
      "url": "https://${env:VAR}/api/security-mcp/mcp/<tenant_id>"
    }
  }
}
```

Set the `VAR` environment variable with your Checkmarx API endpoint.
