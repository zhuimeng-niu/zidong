# Copilot Instructions for zidong

This repository contains a Cloudflare Worker script that is automatically synchronized from an external source.

## Architecture

- **Main Component**: `_worker.js` - A single-file Cloudflare Worker handling HTTP requests.
- **Data Flow**: Receives HTTP requests, processes them, and returns responses. Specific logic depends on the synced version.
- **External Dependencies**: Relies on Cloudflare's runtime environment and any APIs called within the worker.

## Developer Workflows

- **Building/Testing**: No local build required. The worker is deployed directly to Cloudflare.
- **Deployment**: Use Cloudflare Wrangler CLI or the dashboard. The GitHub Actions workflow handles automatic updates.
- **Debugging**: Use Cloudflare's dashboard logs or `wrangler tail` for real-time logs.

## Conventions

- **Automatic Syncing**: `_worker.js` is updated automatically by the GitHub Actions workflow. Manual edits will be overwritten.
- **Version Tracking**: `version.txt` tracks the current version, updated with each sync.
- **Workflow**: `.github/workflows/niu.yml` runs the sync process, likely on a schedule or trigger.

## Key Files

- `_worker.js`: The worker script.
- `version.txt`: Version information.
- `.github/workflows/niu.yml`: Automation for syncing the worker.

When making changes, focus on the workflow or configuration, not the worker code itself.