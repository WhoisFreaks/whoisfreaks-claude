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

On install, Claude Code prompts you for your free WhoisFreaks API key (from
https://billing.whoisfreaks.com/signup) and stores it securely in the plugin's
config — it is sent as an `X-API-Key` header, never in a URL. Run `/mcp` and you
should see **whoisfreaks** connected with 22 tools. See
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

## License

Released under the [MIT License](LICENSE) — you are free to use, copy, modify
and redistribute this marketplace manifest and its command definitions.

The MIT license covers **only the files in this repository** (the install
manifest and slash-command prompts). It does **not** grant access to the
WhoisFreaks API itself: each user needs their own WhoisFreaks API key, and all
API usage is governed by the
[WhoisFreaks Terms of Service](https://whoisfreaks.com/terms) and
[Privacy Policy](https://whoisfreaks.com/privacy-policy).
