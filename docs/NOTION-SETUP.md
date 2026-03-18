# Notion Setup Guide

This guide walks you through setting up the Notion database required for the `/research-plan` skill to automatically publish research briefs.

---

## Prerequisites

- A Notion workspace (free or paid)
- Notion MCP connected to your Claude environment ([setup guide](https://developers.notion.com/guides/mcp/get-started-with-mcp))

---

## Step 1: Create the Research Repository Database

Create a new **inline database** in Notion (or a full-page database) with the following name and properties.

**Database Name:** `Research Repository`

### Properties

| #   | Property                   | Type   | Options / Notes                                                                                                                        |
| --- | -------------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | **Title**                  | Title  | Research project or brief name                                                                                                         |
| 2   | **App**                    | Select | Your products/projects. Examples: `Apple`, `Bloomberg`, `Airtable`, `Microsoft`, `Revolut`. Add your own as needed.                    |
| 3   | **Research Type**          | Select | `Generative`, `Descriptive`, `Evaluative`, `Causal`, `Concept Testing`, `Usability Testing`, `User Interviews`, `Competitive Analysis` |
| 4   | **Status**                 | Status | To Do: `Planning` · In Progress: `In Progress`, `Analyzing` · Complete: `Complete`                                                     |
| 5   | **Main Research Question** | Text   | The core question being answered                                                                                                       |
| 6   | **Target Group**           | Text   | Who will be studied                                                                                                                    |
| 7   | **Success Metrics**        | Text   | How success is measured                                                                                                                |
| 8   | **Date Started**           | Date   | When the research kicked off                                                                                                           |
| 9   | **Date Completed**         | Date   | When findings were delivered                                                                                                           |
| 10  | **Timeline**               | Text   | Expected duration or weekly breakdown                                                                                                  |
| 11  | **Researcher**             | Person | Who's leading this research                                                                                                            |
| 12  | **Team/Tribe**             | Text   | Which team owns this                                                                                                                   |
| 13  | **Key Findings**           | Text   | Summary of insights (filled after research)                                                                                            |
| 14  | **Business Impact**        | Select | `Higher Quality`, `More Sales`, `Lower Cost`, `Multiple`                                                                               |
| 15  | **Next Steps**             | Text   | What's needed after research completes                                                                                                 |

### About the Status Property

Use Notion's **Status** property type (not a regular Select). This gives you the built-in Kanban grouping with To Do → In Progress → Complete categories:

- **To Do:** Planning
- **In Progress:** In Progress, Analyzing
- **Complete:** Complete

---

## Step 2: Create Database Views

Set up the following views for different ways to browse your research.

### 1. All Research (Table)

- Default table view showing all properties
- Sort by Date Started (newest first)

### 2. By App (Gallery)

- Gallery view grouped or filtered by **App**
- Card shows: Title, App, Research Type, Status
- Sort by Date Started (newest first)
- Color-code cards by App for quick scanning

### 3. Timeline

- Timeline view
- Timeline by: **Date Started**
- Timeline end: **Date Completed**
- Useful for seeing research cadence and overlaps

### 4. By Status (Board)

- Board view grouped by **Status**
- Columns: Planning → In Progress → Analyzing → Complete
- Card shows: Title, Researcher, Date Started, Research Type
- Drag cards between columns as research progresses

---

## Step 3: Add Sample Entries (Optional)

To test your setup, add a few sample entries:

| Title                            | App         | Research Type | Status      |
| -------------------------------- | ----------- | ------------- | ----------- |
| Calendar Widget Usability        | Rabobank    | Evaluative    | Complete    |
| Trader Workflow Discovery        | DexScreener | Generative    | In Progress |
| DeFi Dashboard User Segmentation | Resolv      | Descriptive   | Planning    |
| Buyer Search Behavior            | Qogita      | Generative    | Complete    |

---

## Step 4: Connect to the Skill

### Get Your Data Source ID

Once the database is created, you need the **data source ID** so the skill knows where to publish.

**In Claude Code:**

1. Connect Notion MCP: `claude mcp add --transport http notion https://mcp.notion.com/mcp`
2. Complete the OAuth flow
3. Ask Claude: "Fetch my Research Repository database and give me the data source ID"
4. Claude will return something like: `collection://327eac60-25b7-80d4-8313-000b001015cc`

**In claude.ai:**

1. Go to Settings → Connectors → Notion and connect your workspace
2. Ask Claude: "Fetch my Research Repository database schema"

### Update the Config

Add your data source ID to the skill's config file at `.claude/skills/research-plan/config.json`:

```json
{
  "notion_data_source_id": "YOUR-DATA-SOURCE-ID-HERE",
  "default_app": "Apple",
  "researcher_name": "Your Name",
  "apps": ["Apple", "Bloomberg", "Microsoft", "Airtable", "Revolut"]
}
```

Replace `YOUR-DATA-SOURCE-ID-HERE` with the ID from the previous step.

---

## Step 5: Verify the Connection

Run the `/research-plan` skill and confirm that:

1. A new entry appears in your Research Repository database
2. All properties (App, Status, Research Type, etc.) are filled correctly
3. The page content contains the full 11-section research brief
4. The entry appears in your Board and Gallery views

---

## Design Principles

- **Clean, minimal layout** — Let the content breathe
- **Color-code by App** — Use Notion's select colors for quick visual scanning
- **Show key insights at a glance** — Main Research Question and Status visible in all views
- **Link to full briefs** — Each database entry's page contains the complete research brief
- **Living document** — Update Key Findings, Next Steps, and Status as research progresses

---

## Customization

### Adding New Apps

Add new options to the **App** select property in Notion, then update the `apps` array in `config.json`.

### Adding New Research Types

The default types are based on Erika Hall's _Just Enough Research_ framework. Add new options to the **Research Type** select property as needed.

### Changing Properties

If you modify the database schema, update the publish instructions in `.claude/skills/research-plan/SKILL.md` to match your new property names and types.

---

## Troubleshooting

| Problem                       | Solution                                                                                  |
| ----------------------------- | ----------------------------------------------------------------------------------------- |
| Skill can't find the database | Verify the data source ID in `config.json` matches your Notion database                   |
| Properties aren't mapping     | Check that property names in SKILL.md exactly match your Notion database (case-sensitive) |
| OAuth expired                 | Reconnect Notion MCP — tokens expire periodically                                         |
| Wrong workspace connected     | Disconnect and reconnect, selecting the correct workspace during OAuth                    |
| Status property not working   | Make sure you used Notion's **Status** type, not a regular Select                         |
