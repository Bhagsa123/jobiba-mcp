# Installing Jobiba MCP (for AI agents such as Cline)

Jobiba is a hosted remote MCP server. There is nothing to download, build or run locally, and no API key.

## Steps

1. Ask the user which server they want:
   - Job seekers: `https://jobiba.com/mcp/jobs`
   - Employers and recruiters: `https://jobiba.com/mcp/hiring`
   - Both: `https://jobiba.com/mcp`
2. Add it to the MCP settings file as a remote (Streamable HTTP) server:

```json
{
  "mcpServers": {
    "jobiba": {
      "type": "streamableHttp",
      "url": "https://jobiba.com/mcp/jobs"
    }
  }
}
```

   If the client does not accept `streamableHttp`, use `"type": "http"`, or leave `type` out.
3. Reload the MCP servers. Public tools (`search_jobs`, `get_job`, `salary_research`, `company_insights`) work at once.
4. Personal and employer tools answer HTTP 401 the first time. The client then opens Jobiba's sign-in in the browser (OAuth 2.1 with PKCE and dynamic client registration). After the user signs in, retry the tool.

## Check it works

Call `search_jobs` with `{"query": "data analyst", "location": "Bengaluru"}`. It returns live jobs with links.

Full guide: https://jobiba.com/developers
