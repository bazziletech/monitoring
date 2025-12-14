# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an [Upptime](https://upptime.js.org) uptime monitoring repository for Bazzile services. Upptime is a GitHub-powered open-source uptime monitor that uses GitHub Actions for monitoring, GitHub Issues for incident reports, and GitHub Pages for the status page.

## Architecture

- **Configuration**: All monitoring configuration is in `.upptimerc.yml` - this is the primary file to edit
- **Workflows**: GitHub Actions in `.github/workflows/` are auto-generated from the Upptime template - do not edit directly
- **Data**: 
  - `api/` - JSON response time and uptime data per monitored site
  - `history/` - YAML history files and summary.json
  - `graphs/` - Generated response time graphs

## Monitored Sites

Configured in `.upptimerc.yml`:
- Website: https://www.bazzile.com
- APP: https://www.bazzile.app
- API: https://www.bazzile.app/api (GraphQL POST endpoint)

## Configuration Changes

To modify monitoring:
1. Edit `.upptimerc.yml` to add/remove sites or change settings
2. Commit and push - workflows will regenerate automatically
3. Status page updates at https://monitoring.bazzile.ch

Key `.upptimerc.yml` sections:
- `sites`: List of endpoints to monitor with optional method, body, headers
- `status-website`: Theme and branding for the public status page
- `assignees`: Users assigned to incident issues

## Important Notes

- Workflow files have a header warning not to edit directly - they are overwritten weekly by Upptime template updates
- The `renovate.json` manages dependency updates
- Uptime checks run every 5 minutes via cron schedule
