# Environment Setup for Claude Architect

To build the 5 core systems for the Claude Certified Architect curriculum, the following environment and tools are required:

## Core AI Stack
- **Anthropic API**: Access to Claude 3.5 Sonnet and Opus models.
- **Agent SDK**: Python/Node.js SDKs for Anthropic.
- **Claude Code**: The official CLI tool from Anthropic for agentic development.
- **MCP (Model Context Protocol)**: Libraries and tools to integrate MCP.

## Infrastructure
- **Backend Services**: Fly.io for deploying Python/Node backend systems (as per the delivery pilot template standard).
- **Secrets Management**: Doppler to securely handle Anthropic API keys.
- **Local Dev**: VS Code or Cursor, properly configured with Python/Node environments.

## Setup Steps
1. Create an Anthropic developer account and generate API keys.
2. Store API keys securely in Doppler under the project `claude-architect`.
3. Install `claude-code` CLI locally.
4. Initialize a Python or Node project in `5_Symbols` for the actual implementation.
