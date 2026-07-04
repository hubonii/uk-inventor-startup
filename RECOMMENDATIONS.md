# Best Practices & Recommendations

Setting up the MCP servers and skills is only the first step. To get the most out of your autonomous research agent, follow these strategic recommendations.

## 1. Multi-Agent Workflows
For deep startup research, use sub-agents to parallelize your work.
- **Example workflow:** Invoke a `research` subagent to crawl a competitor's website using Firecrawl, while instructing the primary agent to analyze the startup's GitHub repository. 
- Use the `/teamwork-preview` slash command when dealing with massive repositories or highly complex market research tasks.

## 2. Managing Long-Term Memory
Since startup due diligence can take weeks, managing the agent's context is critical.
- Ensure the `memory` MCP server is active during all sessions.
- Periodically ask the agent to "summarize our findings on [Startup Name] and save it to the Knowledge Base."
- Use the `/goal` command to allow the agent to run overnight background tasks (like scraping and indexing 100+ PDFs or financial documents).

## 3. Safe Legal & Compliance Research
When analyzing GDPR compliance or legal contracts:
- Never rely purely on the agent's internal weights.
- Always instruct the agent to use `Brave Search` to find official government documentation or use the `pdf` skill to read verified legal contracts.
- **Disclaimer:** The agent can identify risks in privacy policies, but it does not replace a lawyer during funding rounds.

## 4. Evaluating Architecture (CTO Decision Making)
When doing technical due diligence on a startup:
- Ask the agent to use the `github` MCP server to list all pull requests in the last 30 days to measure developer velocity.
- Have the agent parse the `package.json` or `requirements.txt` and check against known CVEs.
- Ask the agent to generate Mermaid architecture diagrams based on the codebase to visualize their infrastructure.

## 5. Alternative Tooling Considerations
- **Playwright vs. Puppeteer**: Playwright is recommended over Puppeteer for web automation because it handles modern SPA (Single Page Applications) and anti-bot captchas more gracefully.
- **SQLite vs. Postgres**: Use the SQLite MCP for quick, portable financial data analysis. Only spin up the Postgres MCP if the startup provides a massive SQL dump of their production database.

---
**Conclusion:** Your environment is now structurally prepared. Once you have installed the tooling and added the API keys, you can begin your research!
