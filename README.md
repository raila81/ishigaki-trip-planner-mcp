# Ishigaki Ferries & Islands MCP server

Answers how to get from Ishigaki to the Yaeyama islands and what to do there: today's ferry status, the next boats on each route with fares, island-hopping day plans, the cancellation record, which island fits you, an island day guide and the best time to visit. Each answer names its source and links to the matching page on ishigaki.info.

- **Website:** [ishigaki.info](https://ishigaki.info)
- **Documentation:** [ishigaki.info/developers](https://ishigaki.info/developers/)
- **Endpoint:** `https://ishigaki.info/mcp` (MCP Streamable HTTP, public, no authentication, no API key)

## Tools

- `ferry_status`: Whether the ferries from Ishigaki to Taketomi, Kohama, Kuroshima, Iriomote (Ohara, Uehara), Hatoma and Hateruma are running today, per operator (Anei Kanko, YKF)...
- `next_ferries`: The next scheduled boats on one route from the operators' published timetables, in Japan time, with fares
- `plan_island_day`: Earliest published boats for up to three islands in one day from Ishigaki: out, back, time on each island, when you are back in Ishigaki, or why it cannot be done
- `ferry_cancellation_history`: Day-by-day record of cancellations per route since 7 November 2026, from readings of the operators' status pages several times a day...
- `list_routes`: The seven ferry routes from Ishigaki Port with operators, crossing time, boats a day, first and last boat, and the page that explains each
- `which_island`: Ranks the six islands reachable by ferry from Ishigaki (Taketomi, Iriomote, Kohama, Kuroshima, Hatoma, Hateruma) for the traveller's time, interests, month, children...
- `island_guide`: A recommended day on one island from Ishigaki, step by step (when, what, source), plus getting around, food, children, rainy days, staying overnight, local rules...
- `best_time`: Ishigaki and Yaeyama month by month: JMA temperature, rain and sunshine normals, typhoon approaches, 2025 visitor numbers, and what applies that month...

All tools are read-only and stateless. Tool inputs are not stored or logged; see the privacy page.

## Connect

Any MCP client that supports remote servers:

```json
{
  "mcpServers": {
    "ishigaki-ferries": {
      "type": "streamable-http",
      "url": "https://ishigaki.info/mcp?src=mcp"
    }
  }
}
```

Quick test:

```bash
curl -s -X POST 'https://ishigaki.info/mcp?src=mcp' -H 'Content-Type: application/json' -H 'Accept: application/json, text/event-stream' -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

This repository holds the listing metadata only. The server itself is a hosted service run by the Ishigaki Ferries & Islands website (https://ishigaki.info); see [privacy](https://ishigaki.info/privacy/) and [terms](https://ishigaki.info/terms/).
