# Fi-Plan MCP Server

[Fi-Plan](https://www.fi-plan.in) is a month-by-month financial simulator for
Indian salaries — income, taxes, EMIs, SIPs, and up to 50 years of net worth.

This repository is the public descriptor for the **hosted** Fi-Plan MCP server.
The server itself is not open source; the endpoint below is publicly reachable
and speaks MCP over Streamable HTTP (JSON-RPC 2.0).

## Endpoint

```
https://www.fi-plan.in/mcp
```

## Tools

Anonymous tools (no account required, IP rate limited):

| Tool | What it does |
|---|---|
| `loan_amortization` | Real monthly amortization schedule, with optional prepayments |
| `loan_refinance` | Refinance analysis: old loan vs new loan, break-even |
| `asset_projection` | Projects asset / portfolio growth over a horizon |
| `simulate_plan` | Runs a full year-by-year projection from a `plan_json` payload |

Authenticated tools (your plans, cashflows, loans, assets, net worth) are
available with an API token or OAuth. Create a token at
<https://www.fi-plan.in/profile>.

## Client configuration

Claude Desktop / Cursor / any MCP client:

```json
{
  "mcpServers": {
    "fi-plan": {
      "url": "https://www.fi-plan.in/mcp"
    }
  }
}
```

Authenticated (optional):

```json
{
  "mcpServers": {
    "fi-plan": {
      "url": "https://www.fi-plan.in/mcp",
      "headers": { "Authorization": "Bearer fp_your_token_here" }
    }
  }
}
```

## Discovery

- Tools list: <https://www.fi-plan.in/api/public/tools>
- OpenAPI: <https://www.fi-plan.in/api/public/openapi.json>
- `llms.txt`: <https://www.fi-plan.in/llms.txt>

## License

The contents of this repository (documentation) are MIT licensed.
The Fi-Plan application and MCP server are proprietary — see
<https://www.fi-plan.in> for terms.
