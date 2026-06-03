# Changelog

All notable changes to the Checkmarx Security MCP Server will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2026-06-04

### Added

#### Core MCP Server
- Initial release of the Checkmarx Security MCP Server
- Multi-protocol transport support: `stdio`, `sse`, and `http` (streamable HTTP)
- Modular architecture enabling independent team contributions per module

#### Authentication
- API Key authentication via `Authorization` header
- OAuth2 authentication with Dynamic Client Registration (DCR) support
- JWT signature verification with JWKS endpoint caching (5-minute TTL)
- Stale-cache fallback for IAM outage resilience
- Redis-backed session caching with in-memory fallback

#### Scanning Tools (7 tools)
- `planScan` — Recommend scan engines before triggering
- `triggerScan` — Start scans in CLI (local code) or API (repository URL) mode
- `getScanDetails` — Retrieve scan status, progress, and severity summary
- `getLatestScans` — Fetch recent scans for a project
- `listScans` — List scans with status, date range, and branch filters
- `listFindings` — List vulnerabilities with severity filtering
- `getFindingDetails` — Get detailed information for a specific finding

#### Project Management Tools (4 tools)
- `resolveProject` — Resolve a project by name (exact match, candidates, or not found)
- `createProject` — Create a new Checkmarx One project
- `listProjects` — Browse or search all projects
- `getProjectConfig` — Retrieve full project configuration

#### Application Management Tools (4 tools)
- `listApplications` — Browse or search applications
- `createApplication` — Create a new application
- `getApplicationDetails` — Get application details by ID
- `associateProject` — Link projects to an application

#### Analytics & Risk Tools (7 tools)
- `listProjectsOverview` — High-level project security status
- `getProjectsOverviewAggregate` — Organization-wide project metrics
- `getApplicationsOverviewCount` — Application count summary
- `getApplicationsOverviewAggregate` — Organization-wide application metrics
- `getTenantVulnerabilitiesSummary` — Time-windowed vulnerability analytics
- `getRiskSummary` — Overall risk assessment
- `listRiskResults` — Risk findings with filtering
- `updateRiskResultStatus` — Update finding status (TO_VERIFY, CONFIRMED, URGENT, NOT_EXPLOITABLE)

#### Remediation Tools (3 tools)
- `codeRemediation` — AI-generated fixes for SAST findings, secrets, and IaC misconfigurations
- `packageRemediation` — Safe upgrade paths for vulnerable open-source packages (npm, Maven, PyPI, Go, NuGet)
- `imageRemediation` — Secure base image alternatives for vulnerable container images

#### MCP Resources (5 resources)
- `cxone://engines` — Supported scan engine definitions (SAST, SCA, KICS, Secret Detection)
- `cxone://severity-levels` — Vulnerability severity level definitions
- `cxone://finding-states` — Finding lifecycle states
- `cxone://scan-statuses` — Scan execution status definitions
- `cxone://capabilities` — Server capabilities and tool routing rules

#### MCP Prompts (1 prompt)
- `security-scan` — Guided end-to-end scan workflow with engine selection, project resolution, and results

#### Scan Engines Support
- **SAST** — Static Application Security Testing (30+ languages)
- **SCA** — Software Composition Analysis (open-source dependencies)
- **KICS** — Infrastructure as Code security (Terraform, CloudFormation, Kubernetes, Dockerfile)
- **Secret Detection** — Hardcoded credentials, API keys, and tokens

#### Integrations
- Checkmarx One platform (SAST, SCA, KICS, Container Security)
- Dustico API for supply-chain malicious package detection
- OpenTelemetry for distributed tracing and structured logging

#### IDE & Client Support
- Windsurf IDE (API Key and OAuth2)
- IntelliJ IDEA / GitHub Copilot (API Key)
- Claude Desktop / Claude Code (API Key)

---

[1.0.0]: https://github.com/cx-anand-nandeshwar/security-mcp-marketplace/releases/tag/v1.0.0
