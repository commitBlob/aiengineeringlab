# AI Engineering Lab — GitHub Enterprise AI controls

### Purpose
This page describes the AI-related controls configured on the DSIT AI Engineering Lab GitHub Enterprise. It covers agents, GitHub Copilot, and Model Context Protocol (MCP) servers.

### Who this is for
Tech leads and department owners who need to understand what is enabled, restricted, or pending configuration.

### Contents

This page covers:

- agents
- GitHub Copilot configuration
- MCP servers

---

## Agents

Agents in GitHub allow AI to autonomously take actions within repositories and workflows, from reviewing pull requests to creating branches and iterating on code. The AI Engineering Lab enterprise has Copilot Code Review enabled, with the Copilot Coding Agent available but not yet configured.

| Agent or setting | Value | Description |
|---|---|---|
| Copilot Coding Agent | Enabled | Available for autonomous PR creation and issue resolution |
| Copilot Code Review | Enabled | AI-powered code review across the enterprise with inline feedback |

### Guidance for tech leads

The following agent features are active:

- Copilot Code Review is enabled, allowing you to request AI code reviews on pull requests directly within GitHub
- Agent Mode in IDE chat (VS Code, JetBrains, and others) is configured under Copilot clients

---

## GitHub Copilot configuration

GitHub Copilot provides AI-assisted code completion, chat, and code review within supported IDEs, GitHub.com, mobile, and the CLI. Enterprise-level configuration controls privacy, feature availability, and accessible models.

### Access management
Licences are allocated at enterprise level and distributed to individual users. To request additional seats or onboard new teams, contact the AI Engineering Lab.

### Models
The enterprise has 13 models enabled. No custom models are configured. Organisations may configure a subset of the following for their teams:

- Anthropic Claude Sonnet 4
- Anthropic Claude Sonnet 4.5
- Anthropic Claude Haiku 4.5
- Anthropic Claude Opus 4.5
- Google Gemini 2.5 Pro
- Google Gemini 3 Pro
- Google Gemini 3 Flash
- OpenAI GPT-5 mini
- OpenAI GPT-5.1
- OpenAI GPT-5.1-Codex
- OpenAI GPT-5.1-Codex-Mini
- OpenAI GPT-5.1-Codex-Max
- OpenAI GPT-5.2-Codex

### Privacy settings

| Setting | Value | Description |
|---|---|---|
| Suggestions matching public code | Blocked | Prevents Copilot from suggesting code that directly matches public repositories, reducing IP and licensing risk |

### Feature policies

| Feature | Value | Description |
|---|---|---|
| Policies for enterprise-assigned users | Disabled everywhere | Centralises policy control |
| Spark (Preview) | Disabled everywhere | Micro-app builder disabled |
| Force Spark repo into organisation | Off | Companion setting to Spark |
| Editor preview features | Disabled everywhere | Prevents use of experimental IDE features |
| Copilot can search the web | Enabled everywhere | Uses Bing for up-to-date queries |
| Copilot-generated commit messages | Enabled everywhere | Suggested commit messages on GitHub.com |

### Copilot Spaces and memory

| Feature | Value | Description |
|---|---|---|
| Copilot Spaces (view and create) | Enabled everywhere | Persistent AI workspaces |
| Copilot Spaces individual access | Enabled everywhere | Personally owned Spaces allowed |
| Copilot Spaces individual sharing | Enabled everywhere | Sharing allowed when no enterprise data is involved |
| Copilot Memory (Preview) | Disabled everywhere | Repository memory disabled |

### Billing and premium requests

| Setting | Value | Description |
|---|---|---|
| Custom models via API key | Disabled everywhere | Only enterprise-approved models allowed |
| Premium request paid usage | Enabled | Overspend covered by DSIT until programme end |

If your team requires additional or custom models, raise a request with AI Engineering Lab. All changes are assessed against DSIT data governance requirements.

### Metrics and usage

| Setting | Value | Description |
|---|---|---|
| Copilot metrics API | Enabled | Query usage patterns via API |
| Copilot usage dashboard (Preview) | Enabled everywhere | Visual dashboard and API access |

### Copilot clients

| Client | Value | Description |
|---|---|---|
| Copilot in GitHub.com | Let organisations decide | Chat and knowledge base search |
| Copilot CLI (Preview) | Let organisations decide | Terminal assistance |
| Copilot in GitHub Desktop | Enabled everywhere | Desktop AI assistance |
| Copilot Chat in the IDE | Enabled everywhere | Primary developer interface |
| Copilot Chat in GitHub Mobile | Disabled everywhere | Mobile not supported |
| Copilot Agent Mode in IDE Chat | Enabled everywhere | Multi-step reasoning and iteration |

### Content exclusions

#### Secrets, keys, and credentials
```
**/*.key
**/*.pem
**/*.keystore
**/credentials.json
**/serviceaccount.json
**/.env
**/.env.local
**/.env.production
**/.env.staging
**/secrets.json
**/appsettings.*.user.json
**/appsettings.Local.json
**/appsettings.Secrets.json
**/Web.Secret.config
**/Web.Local.config
**/App.Secret.config
**/App.Local.config
src/main/resources/application-prod.yml
src/main/resources/application-prod.properties
src/main/resources/application-secrets.yml
src/main/resources/application-secrets.properties
```

#### Dependencies and package caches
```
node_modules/**
**/__pycache__/**
**/*.egg-info/**
```

---

## MCP servers

Model Context Protocol (MCP) allows Copilot agents to connect to external tools and services. MCP is disabled at the enterprise level.

| Setting | Value | Description |
|---|---|---|
| MCP servers in Copilot | Disabled everywhere | No external tool connections allowed |
| MCP Registry URL (Preview) | Not configured | No registry defined |
| Restrict MCP access to registry servers | Disabled | Not applicable without a registry |

---
