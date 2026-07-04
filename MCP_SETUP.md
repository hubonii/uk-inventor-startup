# MCP Server Configuration

This document outlines the required MCP servers, where to get their API keys, and how to configure them for the agent.

## Required API Keys

Before starting, register for the following services to get your API keys. Most offer generous free tiers.

### 1. Firecrawl (Web Scraping & Crawling)
Essential for bypassing anti-bot protections and converting heavy startup websites into clean Markdown.
- **Get it here:** [Firecrawl Dashboard](https://www.firecrawl.dev/)
- **Cost:** Free tier available (500 credits).

### 2. Tavily (AI Search)
Specifically designed for AI agents to get direct answers and deep research, not just blue links.
- **Get it here:** [Tavily API](https://tavily.com/)
- **Cost:** Free tier available (1,000 searches/month).

### 3. Brave Search (Unfiltered Web Search)
Excellent for competitor analysis without SEO spam filtering.
- **Get it here:** [Brave Search API](https://brave.com/search/api/)
- **Cost:** Free tier available (2,000 calls/month).

### 4. GitHub
Required for the agent to read repository contents, review pull requests, and analyze startup codebases.
- **Get it here:** [GitHub Personal Access Tokens](https://github.com/settings/tokens)
- **Permissions:** Read access to repos.

---

## MCP Server Installations

The following MCP servers have been successfully added to your agent's configuration (`mcp_config.json`) and are now active:

### 🧠 Core Memory & Logic
1. **Memory Server** (`@modelcontextprotocol/server-memory`)
2. **Sequential Thinking** (`@modelcontextprotocol/server-sequential-thinking`)
3. **Filesystem** (`@modelcontextprotocol/server-filesystem` mapped to your workspace)

### 🌍 Research & Web
1. **Firecrawl** (`@mendable/firecrawl-mcp-server`) - Configured with your API key
2. **Tavily** (`@tavily/mcp-server`) - Configured with your API key
3. **GitHub** (`@modelcontextprotocol/server-github`) - Configured with your Personal Access Token

### 🗄️ Data & DB Analysis
For parsing financial data or analyzing a startup's backend.

1. **SQLite**
   ```json
   "sqlite": {
     "command": "uvx",
     "args": ["mcp-server-sqlite", "--db-path", "d:\\my pc H\\السفر\\uk inventor\\research.db"]
   }
   ```

2. **PostgreSQL**
   ```json
   "postgres": {
     "command": "npx",
     "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://user:pass@localhost/dbname"]
   }
   ```

### 📄 Academic & Legal Research
If you are researching deep-tech startups, these are invaluable.

- **ArXiv & Semantic Scholar:** Use the pre-existing skills `literature-search-arxiv` and `literature-search-openalex` included in your agent framework. No additional MCP setup is required.
