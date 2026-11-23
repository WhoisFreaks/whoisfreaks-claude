# WhoisFreaks — Claude Code plugin marketplace

Official [Claude Code](https://docs.claude.com/en/docs/claude-code) plugin
marketplace for [WhoisFreaks](https://whoisfreaks.com): domain, DNS, IP, SSL and
threat-intelligence tools for Claude, via the hosted WhoisFreaks MCP server.

## Install (end users)

```bash
/plugin marketplace add WhoisFreaks/whoisfreaks-claude
```

```bash
/plugin install whoisfreaks@whoisfreaks
```

> Replace `WhoisFreaks/whoisfreaks-claude` with the actual public GitHub repo
> (`owner/name`) this folder is pushed to.

Before first use, set your free API key (from
https://billing.whoisfreaks.com/signup) so Claude Code can authenticate — it is
sent as an `X-API-Key` header, never in a URL:

```bash
export WHOISFREAKS_API_KEY="your-api-key-here"
```

Add that to your shell profile, restart Claude Code, run `/mcp`, and you should
see **whoisfreaks** connected with 22 tools. See
[`plugins/whoisfreaks/README.md`](plugins/whoisfreaks/README.md) for the full
tool list and example prompts.

## Repo layout

```
.claude-plugin/marketplace.json     # marketplace manifest (lists the plugin)
plugins/whoisfreaks/                 # the plugin
  .claude-plugin/plugin.json         #   manifest + inline MCP server config
  commands/domain-intel.md           #   /whoisfreaks:domain-intel slash command
  README.md                          #   user docs
```
