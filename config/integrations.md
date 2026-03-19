# Integrations Configuration

Wire up your tools here. Every skill references these integration keys — change them once, and all skills update.

## Documentation & Knowledge Base

```yaml
docs_tool: notion                    # Options: notion, confluence, coda, google-docs
docs_base_url: ""                    # e.g., https://www.notion.so/your-workspace/
project_hub_template: ""             # Template ID for new project pages
research_db_id: ""                   # Database ID for research repository
insights_db_id: ""                   # Database ID for insights library
```

## Communication

```yaml
comms_tool: slack                    # Options: slack, teams, discord
design_channel: "#design"            # Main design team channel
project_channel_prefix: "#proj-"     # Auto-created per project
stakeholder_channel: "#product"      # Where stakeholder updates go
standup_channel: "#design-standup"   # Daily async updates
```

## Design

```yaml
design_tool: figma                   # Options: figma, sketch, penpot
figma_team_id: ""                    # Your Figma team ID
design_system_file_key: ""           # Main design system file
template_file_key: ""                # Starter template file
token_studio_repo: ""               # GitHub repo for design tokens
```

## Code & Handoff

```yaml
repo_url: ""                         # Main frontend repo
component_library: ""                # e.g., @company/ui
token_format: "css"                  # Options: css, scss, tailwind, style-dictionary
handoff_tool: "figma-dev-mode"       # Options: figma-dev-mode, zeplin, storybook
ci_pipeline: "github-actions"        # Options: github-actions, vercel, netlify
```

## Project Management

```yaml
pm_tool: "linear"                    # Options: linear, jira, asana, shortcut
design_project_prefix: "DES-"        # Ticket prefix for design work
sprint_length_weeks: 2               # Sprint cadence
```

## File Storage

```yaml
storage_tool: "google-drive"         # Options: google-drive, dropbox, sharepoint
research_folder: ""                  # Folder ID for research artifacts
design_assets_folder: ""             # Folder ID for exported assets
```

## Analytics

Product analytics platforms used in `01c-metrics` and `01d-synthesis`.
Store credentials in `.env` (gitignored) — never hardcode here.

```yaml
analytics_primary: "mixpanel"           # Options: mixpanel, amplitude, posthog, ga4, heap, none

mixpanel:
  project_id: ""                        # MIXPANEL_PROJECT_ID env var
  service_account_username: ""          # MIXPANEL_SERVICE_ACCOUNT_USERNAME env var
  service_account_secret: ""            # MIXPANEL_SERVICE_ACCOUNT_SECRET env var
  # Create: Mixpanel > Settings > Service Accounts > Create Service Account
  # Role: Analyst (read-only is sufficient for research)

amplitude:
  api_key: ""                           # AMPLITUDE_API_KEY env var
  secret_key: ""                        # AMPLITUDE_SECRET_KEY env var
  # Found: Amplitude > Settings > Projects > [Project] > General

posthog:
  project_api_key: ""                   # POSTHOG_PROJECT_API_KEY env var
  host: "https://app.posthog.com"       # Override for self-hosted instances

ga4:
  property_id: ""                       # GA4_PROPERTY_ID env var
  # Auth via Application Default Credentials (ADC) or service account JSON

heap:
  app_id: ""                            # HEAP_APP_ID env var
  api_key: ""                           # HEAP_API_KEY env var

# On-chain analytics (crypto/DeFi)
dune:
  api_key: ""                           # DUNE_API_KEY env var
  # https://dune.com/docs/api — free tier available

event_dictionary: ""                    # Link to your analytics data dictionary / doc
                                        # Knowing event names is required for metric queries
```

## Signal Mining Sources

Used by `01-signal-mining` skill. Configure which sources are relevant for your product.

```yaml
signal_sources:
  app_store_id: ""                      # iOS App Store ID (numeric, e.g. 284882215)
  play_store_id: ""                     # Google Play package name (e.g. com.example.app)
  reddit_subreddits:                    # Relevant communities for your product space
    - ""
    - ""
  github_repos:                         # Org/repo pairs for GitHub Issues signal
    - ""
  g2_slug: ""                           # Product slug on G2 (from the URL)
  capterra_slug: ""                     # Product slug on Capterra
  discord_signal_skill: true            # Whether discord-signal-analysis skill is active
  twitter_handle: ""                    # Product/brand Twitter handle to monitor
```

## AI & Automation

```yaml
ai_tool: "claude"                    # Primary AI assistant
automation_tool: "make"              # Options: make, zapier, n8n
mcp_servers:                         # Active MCP connections
  - slack
  - notion
  - figma
  - google-drive
```

## How to Configure

1. Replace empty strings with your actual IDs, URLs, and keys
2. Each skill's `SKILL.md` references these keys as `{{config.docs_tool}}` — the idea is that when you read a step like "Post to Slack," you know which channel from this file
3. When switching orgs, duplicate this file and update values — the skills stay the same
