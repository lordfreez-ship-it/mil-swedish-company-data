# MIL — Swedish company data for AI agents

> **Verified Swedish company information from Bolagsverket and SCB, for AI agents.** Every value says where it came from, how fresh it is and whether the registers agree. Not a register lookup: national search, change history and annual reports.

**Live:** https://www.milquery.com · **MCP:** `https://www.milquery.com/api/mcp` · **Free to try, no account, no key.**

[<img src="https://img.shields.io/badge/VS_Code-VS_Code?style=flat-square&label=Install%20Server&color=0098FF" alt="Install in VS Code">](https://insiders.vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522mil%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fwww.milquery.com%252Fapi%252Fmcp%253Fsrc%253Dreadme%2522%257D)
[<img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Install in Cursor">](https://cursor.com/en/install-mcp?name=mil&config=eyJ1cmwiOiJodHRwczovL3d3dy5taWxxdWVyeS5jb20vYXBpL21jcD9zcmM9cmVhZG1lIn0%3D)

## Connect in one step

**Claude Code**

```bash
claude mcp add --transport http mil https://www.milquery.com/api/mcp?src=readme
```

**Claude (web and desktop, Pro/Max/Team/Enterprise)** — Connectors → *Add custom connector* → paste `https://www.milquery.com/api/mcp?src=readme`.

**ChatGPT** — add a custom connector with `https://www.milquery.com/api/mcp?src=chatgpt`. MIL provides the `search` and `fetch` tools ChatGPT connectors use. No key.

**VS Code / Cursor** — the buttons above, or add this to your MCP config:

```json
{ "servers": { "mil": { "type": "http", "url": "https://www.milquery.com/api/mcp?src=readme" } } }
```

**Any HTTP client** — `GET https://www.milquery.com/v1/companies?name=volvo`

## What you can ask

- *"Check this supplier before we pay: org.nr 556012-5790. Do SCB and Bolagsverket agree, and has anything changed?"*
- *"List building contractors (SNI 41200) in Malmö and flag the ones with active warning signals, such as lost VAT registration or liquidation."*
- *"Show the last three annual reports for this company: revenue, result and equity, year on year."*
- *"Which companies run a workplace in Trelleborg in software development (SNI 62010)?"* (REST: `/v1/workplaces/search`)

MIL answers from the registers, never from memory. If a value is unknown, MIL says *unknown*. If the registers disagree, MIL shows both values instead of picking one.

## Free and paid

| Product | Price per company | What you get |
|---|---|---|
| **Basic** | free (fair use) | Identity: name, organisationsnummer, legal form, SNI, registration date, municipality, status |
| **Verified** | 0.02 USDC | The full current state (VAT, F-tax, employer registration, size, addresses, …), each value with source, verification status and freshness |
| **Intelligence** | 0.08 USDC | Verified + change history, events, digitally filed annual reports with trends, rule-based signals. Charged as Verified when it would add nothing |

Pay per call with **x402** (USDC on Base, no account), or open a **card account** for companies (monthly invoice or prepaid credit, Swedish moms): `GET https://www.milquery.com/v1/billing`.

## What MIL does not do

- No beneficial owners, board members or ownership structure.
- No sanctions, PEP or adverse-media screening.
- No bank-account verification.
- No credit or risk score, and no advice. MIL serves facts with their sources; you draw the conclusions.
- Sweden only.

**Keywords:** Swedish company register · Bolagsverket · SCB Företagsregistret · organisationsnummer · company lookup Sweden · supplier verification · KYB · SNI industry search · annual reports (årsredovisning) · MCP server · x402

## Discovery for machines

- `https://www.milquery.com/llms.txt` — plain-language guide for agents
- `https://www.milquery.com/openapi.json` — REST schema
- `https://www.milquery.com/capabilities` — products, prices, limits
- `https://www.milquery.com/.well-known/mcp.json` — MCP manifest

## About this repository

This is the public home of MIL: documentation, examples and the MCP Registry entry (`server.json`). The service runs at https://www.milquery.com; its source code is not public.

Questions, data problems or feature requests: open an issue in this repository.
