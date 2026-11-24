# WhoisFreaks — Claude Code plugin

Domain, DNS, IP, SSL and threat-intelligence tools for Claude, powered by the
[WhoisFreaks API](https://whoisfreaks.com). Installing this plugin adds **22
WhoisFreaks tools** to Claude Code (CLI and the Claude desktop/web Code tab).

It connects to the hosted WhoisFreaks MCP server — nothing to build, run or
host. Every user brings their **own WhoisFreaks API key**.

This plugin is for **Claude Code**. On claude.ai, Claude Desktop and Cowork, use
the WhoisFreaks connector instead, which signs in with your WhoisFreaks account
(see [Other Claude apps](#other-claude-apps)).

---

## 1. Get a free API key

Sign up at **https://billing.whoisfreaks.com/signup** and copy your API key.

## 2. Install the plugin

```bash
/plugin marketplace add WhoisFreaks/whoisfreaks-claude
```

```bash
/plugin install whoisfreaks@whoisfreaks
```

Claude Code prompts you for your **WhoisFreaks API key** when the plugin loads
and stores it securely in the plugin's config (sent as an `X-API-Key` header —
never in a URL or log). Run `/mcp` — you should see **whoisfreaks** connected
with 22 tools.

---

## What you can ask

```
Who owns apple.com? Give me full WHOIS details.
Show the complete ownership history for whoisfreaks.com.
What are the MX and NS records for github.com?
Where is 1.1.1.1 located, and what ISP runs it?
Is 185.220.101.45 a Tor exit node or a VPN?
Is mycompany.io available to register? Suggest 5 alternatives.
List all known subdomains of tesla.com.
Find recent typosquats of 'paypal'.
Check the SSL certificate for github.com.
How many credits do I have left on my WhoisFreaks key?
```

## The 22 tools

**WHOIS** — `liveWhoisLookup`, `bulkWhoisLookup`, `whoisHistory`, `reverseWhoisLookup`
**IP & ASN WHOIS** — `ipWhoisLookup`, `asnWhoisLookup`
**DNS** — `dnsLookup`, `bulkDnsLookup`, `dnsHistory`, `reverseDnsLookup`
**IP intelligence** — `ipGeolocation`, `bulkIpGeolocation`, `ipSecurity`, `bulkIpSecurity`
**Domain** — `domainAvailability`, `bulkDomainAvailability`, `subdomainLookup`, `domainDiscovery`, `subdomainTyposquatting`, `domainReputation`
**SSL** — `sslLookup`
**Account** — `apiKeyUsage` (costs nothing)

Tools cost the same credits as calling the [API](https://whoisfreaks.com/documentation)
directly; bulk tools cost per item. See the
[credit usage page](https://whoisfreaks.com/documentation/credit-usage).

---

## What the plugin sends, and where

- The plugin runs no code on your machine. It only connects Claude to the hosted
  WhoisFreaks MCP server at `https://mcp.whoisfreaks.com`.
- Each tool call sends the lookup you asked for (domain, IP, ASN, keyword) and
  your API key, in the `X-API-Key` header, to that server, which calls the
  [WhoisFreaks API](https://whoisfreaks.com/documentation) and returns the result.
- Nothing else is sent: no files, chat history or other data from your machine.
- Lookups are handled under the
  [WhoisFreaks Privacy Policy](https://whoisfreaks.com/privacy-policy) and
  [Terms](https://whoisfreaks.com/terms).

## Other Claude apps

- **claude.ai, Claude Desktop and Cowork:** add the WhoisFreaks connector from the
  Connectors directory, or add a custom connector with the URL
  `https://mcp.whoisfreaks.com/oauth` and sign in with your WhoisFreaks account.
- **`claude mcp add` without the plugin:**
  ```bash
  claude mcp add --transport http whoisfreaks https://mcp.whoisfreaks.com/mcp \
    --header "X-API-Key: YOUR_API_KEY"
  ```

## Links

- API docs — https://whoisfreaks.com/documentation
- Billing & keys — https://whoisfreaks.com/billing
- Server source — https://github.com/WhoisFreaks/whoisfreaks-mcp-server
- Support — https://whoisfreaks.com/contact
