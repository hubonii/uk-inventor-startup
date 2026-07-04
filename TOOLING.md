# Base Tooling & Prerequisites

Before setting up the MCP servers, your machine needs to have the foundational tooling installed. This allows the agent to run the servers locally.

## 1. Node.js
Many official MCP servers (Memory, Sequential Thinking, Puppeteer) are built with Node.js and TypeScript.

- **What you need:** Node.js (v18 or higher) and `npx` (comes with Node).
- **How to get it:**
  - Go to [Node.js Official Website](https://nodejs.org/) and download the **LTS (Long Term Support)** installer for Windows.
  - Run the installer and ensure "Add to PATH" is selected.

## 2. Python & uv
Several data-science and research MCP servers (like Fetch, SQLite) are built in Python.

- **What you need:** Python (v3.10 or higher) and the `uv` package manager.
- **How to get Python:**
  - Go to [Python's Windows Downloads](https://www.python.org/downloads/windows/).
  - Download the latest stable 3.1x release. **IMPORTANT:** Check the box that says "Add Python to PATH" during installation.
- **How to get uv:**
  - Open PowerShell and run: `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`

## 3. Git
Git is essential for cloning startup repositories so the agent can analyze their architecture.

- **What you need:** Git for Windows.
- **How to get it:**
  - Go to [Git for Windows](https://git-scm.com/download/win).
  - Download and install it using the default settings.

## 4. Docker (Optional but Recommended)
For isolating databases like PostgreSQL, running containerized servers, or analyzing untrusted code.

- **What you need:** Docker Desktop for Windows.
- **How to get it:**
  - Download from [Docker Desktop](https://www.docker.com/products/docker-desktop/).
  - Note: Requires WSL2 (Windows Subsystem for Linux), which Docker will help you set up during installation.

## 5. Playwright Browsers (For Web Scraping)
To allow the agent to visually inspect and interact with websites:

- **What you need:** Playwright browser binaries.
- **How to get it:**
  - Open PowerShell.
  - Run: `npx playwright install`

---
Once these are installed, you are ready to configure the MCP Servers. See `MCP_SETUP.md`.
