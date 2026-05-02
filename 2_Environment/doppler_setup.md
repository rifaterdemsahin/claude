# 🔐 Doppler Secrets Management Guide

## Why Doppler?

Doppler is the centralized secrets manager for this project. It ensures:
- No secrets in git history
- Environment-specific configs (dev, staging, prod)
- Team-wide access control
- Secret rotation audit trails

## Quick Start

### 1. Install Doppler CLI
```bash
# macOS
brew install dopplerhq/cli/doppler

# Windows (via PowerShell)
scoop install doppler
# or
choco install doppler

# Verify
doppler --version
```

### 2. Authenticate
```bash
doppler login
```

### 3. Project Setup (One-time)
```bash
# Create project (if not exists)
doppler projects create delivery-pilot-template

# Create environments
doppler configs create dev --project delivery-pilot-template
doppler configs create stg --project delivery-pilot-template
doppler configs create prd --project delivery-pilot-template
```

### 4. Add Secrets
```bash
# Set Claude API key (replace with your real key - do not paste in chat)
doppler secrets set ANTHROPIC_API_KEY="" --project delivery-pilot-template --config dev

# Set other required variables
doppler secrets set ANTHROPIC_MODEL="claude-sonnet-4-20250514" --project delivery-pilot-template --config dev
```

### 5. Use in Development
```bash
# Inject env vars and run command
doppler run --project delivery-pilot-template --config dev -- node script.js

# Or download to .env (already gitignored)
doppler secrets download --project delivery-pilot-template --config dev --format env > .env
```

## Required Secrets

| Secret | Description | Example |
|--------|-------------|---------|
| `ANTHROPIC_API_KEY` | Claude API access key | `sk-ant-api03-...` |
| `ANTHROPIC_MODEL` | Default model to use | `claude-sonnet-4-20250514` |

## CI/CD Integration (GitHub Actions)

```yaml
- name: Load secrets from Doppler
  uses: DopplerHQ/cli-action@v1
  with:
    token: ${{ secrets.DOPPLER_TOKEN }}
- name: Build with secrets
  run: doppler run -- npm run build
```

## Fly.io Integration

```bash
# Pass Doppler token to Fly.io
fly secrets set DOPPLER_TOKEN="dp.st.xxx" --app delivery-pilot-template
```

## ⚠️ Security Checklist

- [ ] `.env` is in `.gitignore`
- [ ] `.env.example` contains no real values
- [ ] API keys are rotated if exposed anywhere
- [ ] Doppler project name matches repo name
- [ ] Only `DOPPLER_TOKEN` is in GitHub secrets (not individual API keys)

## Resources

- [Doppler Dashboard](https://dashboard.doppler.com/workplace/5ccb59c6d72db414f3e7/getting-started)
- [Doppler CLI Docs](https://docs.doppler.com/docs/cli)
- [Doppler GitHub Action](https://docs.doppler.com/docs/github-actions)
