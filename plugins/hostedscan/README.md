# HostedScan plugin

The HostedScan plugin adds the HostedScan MCP server at `https://api.hostedscan.com/mcp` and two skills to Claude Code or Cursor. MCP (Model Context Protocol) is the standard that AI assistants use to connect to other services. HostedScan scans websites, servers, and networks for vulnerabilities.

With the server, the assistant can list your workspaces, targets, scans, scheduled scans, and risks. It can also show the fix for a risk and start a scan.

## What you need

- A HostedScan account on the Premium plan or a higher plan, or on the free trial.
- Claude Code or Cursor.

## Install in Claude Code

Add the HostedScan plugin marketplace, then install the plugin:

```
/plugin marketplace add hostedscan/mcp
/plugin install hostedscan@hostedscan
```

Then run `/mcp`, select **plugin:hostedscan:hostedscan**, and sign in.

## Install in Cursor

After the HostedScan plugin is listed in the Cursor Marketplace, open **Customize**, find **HostedScan** in the Cursor Marketplace, and click **Add to Cursor**. Cursor installs the plugin and opens HostedScan to sign in.

## Sign in

The plugin stores no API key. When you sign in, HostedScan asks you to approve the connection:

- **Account:** This menu appears when your workspaces belong to more than one HostedScan account. Choose the account to connect.
- **Workspaces:** Select the workspaces that the assistant can access.
- **Access:** Choose **Read only** to let the assistant view targets, scans, scheduled scans, and risks. Choose **Read and write** to also let it start scans.

Select **Allow access** to finish.

To remove the connection later, open the **Connected Applications** list on the [API & Webhooks](https://hostedscan.com/settings/api) settings page in HostedScan. Open the actions menu on the row of the connection, select **Disconnect**, and confirm.

## Skills

A skill is a set of instructions that the assistant follows for one task. The assistant picks a skill when your request matches it.

- **scan-target:** Scans one target. After the scan finishes, the skill summarizes what the scan found.
- **security-overview:** Summarizes the open risks and the targets with the lowest health grades in your workspaces.

## Example prompts

- "Which of my targets have open critical or high risks?"
- "Run a port scan on my target example.com and tell me what it finds."
- "Which of my targets have the lowest health grade, and how do I fix their worst risks?"

## Help

The help article covers every assistant and the access you approve: https://help.hostedscan.com/help/connect-ai-assistants-with-mcp

For questions, email hello@hostedscan.com.
