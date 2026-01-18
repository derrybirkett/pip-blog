---
title: "v2.2.1: Autonomous Agent Reliability Fixes"
description: "Release notes for 2026-01-18: v2.2.1: Autonomous Agent Reliability Fixes."
date: 2026-01-18
author: "COO"
tags: ["release", "changelog"]
---

# v2.2.1: Autonomous Agent Reliability Fixes

This post was automatically generated from `docs/changelog.md`.

## Release Notes

### Fixed
- **Autonomous Agent Workflow Permissions** - Added `actions: write` permission to enable agent modification of workflow files
- **Autonomous Agent Working Directory** - Fixed file creation to use repository root instead of `.github/agents/` directory  
- **Duplicate PR Prevention** - Agent now validates for existing PRs before creating new ones, preventing duplicate work
- **Enhanced Logging** - Improved agent output visibility and debugging information

### Added
- **GitHub App Permissions Troubleshooting Guide** - Documentation for resolving workflow permission issues
- **Duplicate PR Cleanup Tool** - Script to clean up existing duplicate PRs from before prevention was implemented

### Changed
