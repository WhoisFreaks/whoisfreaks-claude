---
description: Run a WhoisFreaks intelligence report on a domain, IP address, or ASN
---

You have the WhoisFreaks MCP tools available. Build a concise intelligence
report on the target below, calling only the tools that fit what it is.

Target: $ARGUMENTS

Guidance:
- **Domain** → `liveWhoisLookup` (ownership, registrar, dates, nameservers),
  `dnsLookup` with all records (A/AAAA/MX/NS/TXT/SOA), `sslLookup` (certificate
  issuer and expiry), `domainReputation` (risk verdict), and `subdomainLookup`
  if attack surface matters.
- **IP address** → `ipWhoisLookup`, `ipGeolocation`, `ipSecurity` (VPN / proxy /
  Tor / bot signals), and `reverseDnsLookup`.
- **ASN** (e.g. AS15169) → `asnWhoisLookup`.
- **Brand-protection ask** → `domainDiscovery` and `subdomainTyposquatting` for
  typosquats.

Then summarize: who owns it, the infrastructure, security/trust signals, and
anything notable or suspicious. If the target is ambiguous, ask which it is
before spending credits. Note that every tool call except `apiKeyUsage` consumes
WhoisFreaks credits.
