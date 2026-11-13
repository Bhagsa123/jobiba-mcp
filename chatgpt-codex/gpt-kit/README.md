# Jobiba for ChatGPT

Two ways to use Jobiba in ChatGPT. The **app** is the full experience; the **GPT** is a lightweight public-search option.

## A. Jobiba app (full: cards, profile, resumes, applications, interview prep)
1. ChatGPT → Settings → Apps → Advanced settings → enable **Developer mode**.
2. Settings → Apps → **Create app**.
3. Name: `Jobiba Career`, MCP server URL: `https://jobiba.com/mcp`, Authentication: **OAuth**.
4. Create, then start a chat, pick Jobiba from the **+** menu and try "Find React jobs in Bangalore".

(ChatGPT apps are added by URL, there is no zip to upload. Anything in this kit is optional.)

## B. Custom GPT with public search actions
1. ChatGPT → Explore GPTs → Create.
2. Configure → paste `instructions.md` into **Instructions**.
3. Actions → Create new action → Import / paste `actions-openapi.yaml`, Authentication: None.
4. Privacy policy: `https://jobiba.com/privacy`.
