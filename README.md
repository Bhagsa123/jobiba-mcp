# Jobiba MCP: job search, salaries, CVs and hiring for AI assistants

Connect Claude, ChatGPT, Cursor, VS Code, Codex or Gemini CLI to live jobs and salary data from [Jobiba](https://jobiba.com). Job seekers search jobs, check pay, tailor a CV and apply with their confirmation. Employers post jobs, screen applicants and source talent.

This repository holds the client packages and listing files. The server itself is hosted by Jobiba; there is nothing to run or install locally.

## Servers

| URL | Name | For |
|---|---|---|
| `https://jobiba.com/mcp/jobs` | **Jobiba Jobs** | job seekers |
| `https://jobiba.com/mcp/hiring` | **Jobiba Hiring** | employers and recruiters |
| `https://jobiba.com/mcp` | Jobiba Career | both (used by the packages below) |

Transport: Streamable HTTP. Sign-in: OAuth 2.1 with PKCE and dynamic client registration. Public tools (job search, job details, salary research, company research) work without signing in; personal and employer tools open Jobiba's sign-in the first time.

## Use it

**ChatGPT:** [Jobiba in the ChatGPT app directory](https://chatgpt.com/plugins/plugin_asdk_app_6aeb942b20e88191ab6a68e5ae5d1ce1).

**Claude.ai / Claude Desktop:** Settings → Connectors → Add custom connector → `https://jobiba.com/mcp/jobs` or `https://jobiba.com/mcp/hiring`.

**Claude Code (plugin with commands and a skill):**

```
/plugin marketplace add Bhagsa123/jobiba-mcp
/plugin install jobiba-career@jobiba
```

Or the connector only: `claude mcp add --transport http jobiba https://jobiba.com/mcp`

**Cursor / VS Code / any MCP client:** add to `mcp.json`:

```json
{ "mcpServers": { "jobiba": { "url": "https://jobiba.com/mcp/jobs" } } }
```

**Gemini CLI:** `gemini mcp add --transport http jobiba https://jobiba.com/mcp`, or install the extension in [`gemini/`](gemini/).

**Codex:** copy [`chatgpt-codex/`](chatgpt-codex/) into your plugins directory.

## What you can do

**Job seekers**
- Search live jobs by role, skills, place, work mode, job type, experience and pay, shown as job cards.
- Salary research with sample size, trend and pay by experience; compare an offer with the market.
- Tailor a CV to one job. Nothing is invented: every employer, title, date, skill and number must already be in your CV.
- Apply: a preview first, then your explicit confirmation.
- Interview prep, cover letters, company research, saved jobs, job alerts and application tracking.

**Employers**
- Post, edit, close and extend jobs; AI draft of job descriptions.
- Applicant list, AI-assisted screening and stage changes.
- Talent search, shortlist and recruiter outreach (preview, then confirm to send). Candidate contact details are never shown in chat.
- Plans and upgrade links. No payment happens in chat.

## Contents

| Path | What |
|---|---|
| `.claude-plugin/`, `commands/`, `skills/`, `.mcp.json` | Claude Code plugin and marketplace |
| `chatgpt-codex/` | Codex plugin, ChatGPT app manifest, Custom GPT kit |
| `gemini/` | Gemini CLI extension |
| `registry/` | Official MCP Registry entries (`com.jobiba/jobs`, `com.jobiba/hiring`) |

These packages contain only text files and a remote server address. They run no scripts or hooks.

## Data and privacy

Your requests and tool arguments go to Jobiba's servers at `jobiba.com`. After you sign in, Jobiba reads and writes your own profile, CVs and applications for you. Salary figures are summaries of pay listed in job ads, not financial advice.

Privacy policy: https://jobiba.com/privacy · Terms: https://jobiba.com/terms · Documentation: https://jobiba.com/developers · Support: info@jobiba.com

## License

MIT, see [LICENSE](LICENSE).
