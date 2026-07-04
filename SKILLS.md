# Agent Skills configuration

Skills dictate *how* the AI agent approaches specific domains, like analyzing financial models, parsing pitch decks, or auditing code. This document outlines the pre-installed skills to leverage and custom skills to create.

## 1. Built-in Skills to Leverage

Your current agent environment already has several highly relevant skills installed. The agent will automatically use these when requested:

- **`pdf`**: CRITICAL for venture capital due diligence. Use this when asking the agent to read and extract data from pitch decks, whitepapers, or financial reports (e.g., "Extract the cap table from this PDF").
- **`literature-search-arxiv` / `literature-search-openalex`**: Use these when researching the underlying technology of a deep-tech startup (e.g., "Find papers related to the novel battery chemistry they claim").
- **`ml-best-practices`**: Use when analyzing an AI startup's architecture or data pipeline to ensure they are following industry standards, rather than just using buzzwords.
- **`web-interface-guidelines`**: Use when auditing a startup's SaaS product design and UX.

## 2. Recommended Custom Skills

To optimize the environment for VC due diligence and startup research, we recommend creating the following custom skills (by placing a `SKILL.md` inside `.agents/skills/<skill-name>/` in your workspace):

### `startup-validation`
**Purpose**: Guides the agent on how to evaluate a startup's market fit.
- **Instructions**: Instructs the agent to always cross-reference claims using Brave Search, calculate Total Addressable Market (TAM) using verifiable data, and analyze competitor pricing models before concluding.

### `financial-modeling`
**Purpose**: Helps the agent parse CSVs, Excel files, and SQLite databases for financial analysis.
- **Instructions**: Demands the agent use the `sqlite` MCP server to query complex datasets, create visualizations of burn rates, and project runway based on historical spend.

### `security-auditing`
**/Purpose**: For technical due diligence.
- **Instructions**: When cloning a startup's GitHub repo, the agent should look for hardcoded secrets, analyze dependency trees for vulnerable packages, and evaluate their CI/CD pipeline security.

### `legal-gdpr-research`
**Purpose**: Safe analysis of compliance.
- **Instructions**: Forces the agent to cite actual GDPR articles (via web search) when reviewing a startup's privacy policy, rather than hallucinating legal advice.

## 3. How to create a custom skill
1. Create a folder in your workspace: `.agents/skills/my-new-skill/`
2. Create a `SKILL.md` file inside it.
3. Add YAML frontmatter with `name` and `description`.
4. Write the markdown instructions below the frontmatter.
