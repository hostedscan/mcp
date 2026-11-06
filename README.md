# HostedScan for Claude Code and Cursor

This repository has the HostedScan plugin for Claude Code and Cursor. The plugin adds the HostedScan MCP server and two skills to the assistant. MCP (Model Context Protocol) is the standard that AI assistants use to connect to other services. With the plugin, you can ask the assistant about your targets, scans, and risks, and have it start a scan.

The plugin README covers sign-in, the skills, and example prompts: [plugins/hostedscan/README.md](plugins/hostedscan/README.md)

## What you need

- A HostedScan account on the Premium plan or a higher plan, or on the free trial.
- Claude Code or Cursor.

## Install in Claude Code

Add this repository as a plugin marketplace, then install the plugin:

```
/plugin marketplace add hostedscan/mcp
/plugin install hostedscan@hostedscan
```

Then run `/mcp`, select **plugin:hostedscan:hostedscan**, and sign in.

## Install in Cursor

After the HostedScan plugin is listed in the Cursor Marketplace, open **Customize**, find **HostedScan** in the Cursor Marketplace, and click **Add to Cursor**. Cursor installs the plugin and opens HostedScan to sign in.

To add only the MCP server without the skills, add the server to `.cursor/mcp.json` in your project, or to `~/.cursor/mcp.json` for every project:

```json
{
  "mcpServers": {
    "hostedscan": {
      "url": "https://api.hostedscan.com/mcp"
    }
  }
}
```

Cursor opens HostedScan to sign in the first time it uses the server.

## Other assistants

Any assistant that supports remote MCP servers with OAuth sign-in can connect to `https://api.hostedscan.com/mcp`.

The help article has the steps for each assistant: https://help.hostedscan.com/help/connect-ai-assistants-with-mcp

## Repository layout

- `plugins/hostedscan/` has the plugin. The manifests for Claude Code are in `.claude-plugin/`, and the manifests for Cursor are in `.cursor-plugin/`. The MCP server configuration for Claude Code is in `.mcp.json`, and the configuration for Cursor is in `mcp.json`. The skills are in `skills/`.
- `.claude-plugin/marketplace.json` lists the plugin for Claude Code, and `.cursor-plugin/marketplace.json` lists the plugin for Cursor.
- `server.json` describes the server for the MCP Registry.

## License

The contents of this repository are under the MIT License. See [LICENSE](LICENSE).
