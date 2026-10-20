---
name: build-management
description: "Produce reproducible local/CI builds, verify exported packages and report distribution readiness."
---

# Game build and export management

**Primary role:** Game Developer. **Use when:** a playable binary/package, CI pipeline or release candidate is requested.

## Required inputs

- Exact engine/toolchain and platform targets.
- Known project build/test commands and plugin dependencies.
- Approved version/content and release policy.

## Procedure

1. Inspect and verify actual local commands; document missing SDKs, licenses, credentials and targets.
2. Perform clean build with logged dependency/engine versions, output paths and build configuration.
3. Run smoke tests of executable, scene load, input, assets, save path and shutdown where supported.
4. Record build artifact name, size, checksum, platform and required runtime components.
5. Run regression/performance checks specified by the release gate.
6. Hand package and release notes to Director; publishing externally requires explicit user approval.

## Deliverables

- Verified build/export artifact or precise blockage report.
- Reproducible commands, checksums and smoke-test outcomes.

## Validation / done criteria

- [ ] Artifact actually exists at the reported path.
- [ ] Supported target and dependency requirements are documented.
- [ ] No unapproved external upload or store submission.

## Guardrails

- Never claim a cross-platform build from one untested platform.
- Do not put private credentials in logs or packaging output.

**Related skills:** automated-testing, regression-testing, performance-testing.

## Godot integration

For scene work, follow `protocols/mcp-routing.md`. The Cline Director performs MCP operations; workers return file outputs and integration requests. Record evidence through `engine-validation`.
