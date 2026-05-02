# Environment Setup for Delivery Pilot Template

To build features using the Claude API within the 7-stage delivery system, the following environment and tools are required:

## Core AI Stack
- **Anthropic API**: Access to Claude models for AI-powered features.
- **Agent SDK**: Python/Node.js SDKs for Anthropic.
- **Claude Code**: The official CLI tool from Anthropic for agentic development.
- **MCP (Model Context Protocol)**: Libraries and tools to integrate MCP.

## Infrastructure
- **Backend Services**: Fly.io for deploying Python/Node backend systems.
- **Secrets Management**: Doppler to securely handle API keys.
- **Local Dev**: VS Code or Cursor, properly configured with Python/Node environments.

## Setup Steps
1. Create an Anthropic developer account and generate API keys.
2. **Store API keys securely in Doppler** under the project `delivery-pilot-template`.
3. Install `claude-code` CLI locally.
4. Install the Doppler CLI and authenticate.
5. Initialize secrets using `doppler secrets download` or inject at runtime.

## Secrets Management with Doppler

### Doppler Setup
```bash
# Install Doppler CLI (macOS)
brew install dopplerhq/cli/doppler

# Login
doppler login

# Setup project
doppler projects create delivery-pilot-template
doppler configs create dev --project delivery-pilot-template

# Add secrets via CLI (never paste in chat)
doppler secrets set ANTHROPIC_API_KEY="your_key_here" --project delivery-pilot-template --config dev
```

### Using Secrets in Development
```bash
# Run command with Doppler-injected env vars
doppler run -- node your-script.js

# Download to .env for local use (gitignored)
doppler secrets download --format env --project delivery-pilot-template --config dev > .env
```

## ⚠️ Security Rules
- **Never commit `.env` files to git** — they are in `.gitignore`
- **Never paste real API keys in chat or documentation**
- **Rotate exposed keys immediately** if accidentally leaked
- Use `.env.example` as a template only (contains no real values)

## Implementation
- Initialize a Python or Node project in `5_Symbols` for the actual implementation.
- All code that uses `ANTHROPIC_API_KEY` must read from environment variables.
