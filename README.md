# BOE-MCP. MCP Integration with the BOE API

[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README_es.md)
[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)

## DESCRIPTION

**BOE is the Official State Gazette of Spain.**

**Boe-mcp** enables querying consolidated legislation, BOE/BORME summaries, and legal reference data directly through Claude AI and other MCP-compatible clients using the **Model Context Protocol (MCP)**.

Boe-mcp is an MCP server that exposes tools for LLMs to access:
- Consolidated legislation of the Spanish legal system
- Daily BOE and BORME summaries
- Auxiliary tables for legal domains, jurisdictions, and government departments

## KEY FEATURES

- Advanced search of consolidated legislation with date, jurisdiction, and validity filters
- Full legal text retrieval in XML/JSON formats
- Historical BOE and BORME summary queries
- Access to legal reference tables (domains, departments, legal relationships)
- Block-level navigation of legal texts
- Automatic consolidation status validation

## INSTALLATION

### Install with uv

### Prerequisites

- Python 3.10 or higher.
- [uv](https://docs.astral.sh/uv/getting-started/installation/) package manager.

### Installing uv

The first step is to install `uv`, a package manager for Python.  
**It can be installed from the command line**.

On macOS and Linux:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

On Windows:  

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

You can also install it with pip:  

```bash
pip install uv
```

For more information about installing uv, visit the [uv documentation](https://docs.astral.sh/uv/getting-started/installation/).

## INTEGRATION WITH CLIENTS LIKE CLAUDE FOR DESKTOP

1. Go to **Claude > Settings > Developer > Edit Config > `claude_desktop_config.json`**.
2. Add this configuration block under `"mcpServers"`:

```json
"boe_mcp": {
    "command": "uvx",
    "args": [
        "boe_mcp"
    ]
}
```

3. If you have other MCP servers configured, separate them with commas `,`.

## USAGE EXAMPLES

Once configured, you can make queries like:

- "List current state laws on data protection"
- "Show the BOE summary for June 14, 2024"
- "Display the BOE legal domains table"
