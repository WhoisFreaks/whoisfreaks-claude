# WhoisFreaks — Claude Code plugin

Domain, DNS, IP, SSL and threat-intelligence tools for Claude, powered by the
[WhoisFreaks API](https://whoisfreaks.com). Installing this plugin adds **22
WhoisFreaks tools** to Claude Code (CLI and the Claude desktop/web Code tab).

It connects to the hosted WhoisFreaks MCP server — nothing to build, run or
host. Every user brings their **own WhoisFreaks API key**.

---

## 1. Get a free API key

Sign up at **https://billing.whoisfreaks.com/signup** and copy your API key.

## 2. Make the key available to Claude Code

The plugin reads your key from the `WHOISFREAKS_API_KEY` environment variable
(sent as an `X-API-Key` header — the key never appears in a URL or log).

```bash
export WHOISFREAKS_API_KEY="your-api-key-here"
```

Add that line to your shell profile (`~/.bashrc`, `~/.zshrc`, …) so it is set in
every session, then restart Claude Code.

## 3. Install the plugin

```bash
/plugin marketplace add WhoisFreaks/whoisfreaks-mcp-server
```

```bash
/plugin install whoisfreaks@whoisfreaks
```

Restart Claude Code when prompted. Run `/mcp` — you should see **whoisfreaks**
connected with 22 tools.

> Replace `WhoisFreaks/whoisfreaks-mcp-server` with the actual GitHub repo (or
> local path) that hosts this marketplace once it is published.

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

## Alternatives to this plugin

- **claude.ai / Claude Desktop (no plugin):** Settings → Connectors → *Add custom
  connector* → `https://mcp.whoisfreaks.com/mcp`.
- **Raw `claude mcp add`:**
  ```bash
  claude mcp add --transport http whoisfreaks https://mcp.whoisfreaks.com/mcp \
    --header "X-API-Key: YOUR_API_KEY"
  ```

## Links

- API docs — https://whoisfreaks.com/documentation
- Billing & keys — https://whoisfreaks.com/billing
- Server source — https://github.com/WhoisFreaks/whoisfreaks-mcp-server
