# Changelog

All notable changes to the swapi-pilot MCP service are documented here.

## [2.14.5] - 2026-07-05

### Fixed
- Resolved intermittent "server closed the connection unexpectedly"
  errors that could cause API lookups to fail. The service now detects
  and recovers from stale database connections automatically.

### Notes
- Core MCP functionality is stable; no breaking API changes.
- Found an issue? Please report it via GitHub Issues.
