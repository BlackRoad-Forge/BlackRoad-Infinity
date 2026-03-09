# BlackRoad Infinity

**Edge-to-cloud scaling with automated CI/CD workflows.**

Reusable GitHub Actions for the BlackRoad OS ecosystem — auto-deploy, self-healing, security scanning, and dependency management across all repositories.

## Workflows

### Auto Deploy
Detects service type (Next.js, Docker, Node, Python, static) and deploys to the correct target (Cloudflare Pages, Railway, or static hosting) automatically on push to main.

### Self-Healing
Monitors deployments and automatically restarts or redeploys failed services.

### Security Scan
Automated vulnerability scanning across all dependencies and code.

### Dependabot
Automated dependency updates with security patches.

## Usage

Reference these workflows from any BlackRoad repo:

```yaml
# .github/workflows/deploy.yml
name: Deploy
on:
  push:
    branches: [main]

jobs:
  deploy:
    uses: blackboxprogramming/BlackRoad-Infinity/.github/workflows/auto-deploy.yml@main
```

## Supported Targets

| Service Type | Detection | Deploy Target |
|-------------|-----------|---------------|
| Next.js | `next.config.mjs` / `next.config.js` | Cloudflare Pages |
| Docker | `Dockerfile` | Railway |
| Node.js | `package.json` | Railway |
| Python | `requirements.txt` | Railway |
| Static | Default | Cloudflare Pages |

## License

Copyright 2026 BlackRoad OS, Inc. — Alexa Amundson. All rights reserved.
