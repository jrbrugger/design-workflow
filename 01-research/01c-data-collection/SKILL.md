# 01c — Data Collection

## Purpose
Execute the research plan: conduct interviews, pull analytics, run competitive analysis, or collect survey responses. AI assists with preparation, note-taking, and initial organization — but the designer runs the sessions and makes judgment calls.

## When to Use
- After research plan is approved
- Parallel execution of multiple research methods

## Inputs
- Approved research plan (from `01b-research-plan`)
- Screener criteria and recruited participants
- Interview guides, survey instruments, or analysis frameworks

## Outputs
- [ ] **Raw interview notes** → stored in Notion or Google Drive
- [ ] **Interview transcripts** (if recorded) → stored in project folder
- [ ] **Analytics snapshots** → screenshots or exports in project folder
- [ ] **Competitive analysis** → `templates/competitive-matrix.md`
- [ ] **Survey responses** → raw data exported

## Steps

### 1. Prepare interview guide (if applicable)
```
Prompt: "Based on our research objectives: [paste from research plan], 
draft an interview guide using templates/interview-guide.md. 
Structure it as:
- Warm-up (2 min): build rapport
- Context (5 min): understand their world
- Core questions (20 min): tied directly to our research gaps
- Wrap-up (3 min): anything we missed, thank them
Keep questions open-ended. No leading questions. 
Flag any question that could introduce bias."
```

### 2. Run competitive analysis (if applicable)
```
Prompt: "Conduct a competitive analysis for [problem space]. 
Search the web for the top 5-8 products that solve a similar problem. For each:
- Product name and URL
- How they solve the problem
- Key UX patterns used
- Strengths and weaknesses
- Screenshot or key flow description
Format as the competitive matrix template."
```

### 3. Pull analytics (if applicable)
```
Prompt: "Based on our research gaps, I need to analyze:
- [Specific metric or funnel]
- [User behavior pattern]
- [Segment comparison]
Help me formulate the specific queries or dashboard views I need. 
I'll pull the data and paste it back for analysis."
```

### 4. Conduct sessions
_This step is manual — you run the interviews/tests. AI supports prep and follow-up._

```
Prompt: "I just completed an interview. Here are my raw notes: [paste notes].
Clean these up into structured notes:
- Key quotes (verbatim where possible)
- Observations (behavior, emotion, context)
- Surprises (anything unexpected)
- Connections to research gaps
Store in our Notion research database."
```

### 5. Organize raw data
```
Prompt: "I've completed [N] interviews and collected [analytics/competitive/survey] data. 
Organize all raw data into our Notion project page under a 'Raw Research Data' section.
Create a summary index showing what data we collected, from whom, and when."
```

## Integrations
- **Notion**: Store structured interview notes, research database entries
- **Google Drive**: Store recordings, transcripts, exports
- **Slack**: Post progress updates to project channel after each session
- **Calendly/Calendar**: Manage interview scheduling
- **Analytics tool**: (Amplitude, Mixpanel, GA) Pull relevant data

## Templates
- `templates/interview-guide.md` — Semi-structured interview script
- `templates/competitive-matrix.md` — Competitive analysis framework

## Definition of Done
- [ ] All planned research sessions completed
- [ ] Raw notes structured and stored in Notion
- [ ] Analytics data pulled and documented
- [ ] Competitive analysis complete (if planned)
- [ ] All raw data indexed and accessible

## Customization Notes
- If using Dovetail or Condens for research repos, store notes there instead of Notion
- For remote interviews, use Zoom/Teams with transcription enabled — paste transcript for AI structuring
- For guerrilla research, use a simplified 5-question guide and capture notes on your phone
