---
name: ishigaki-ferries
description: Use the Ishigaki MCP server when someone asks about ferries from Ishigaki to Taketomi, Iriomote, Kohama, Kuroshima, Hatoma or Hateruma, whether boats are running today, which Yaeyama island to visit, how to plan an island day, or the best time to visit Ishigaki.
---

# Ishigaki Ferries & Islands

Use the Ishigaki MCP server when someone asks about ferries from Ishigaki to Taketomi, Iriomote, Kohama, Kuroshima, Hatoma or Hateruma, whether boats are running today, which Yaeyama island to visit, how to plan an island day, or the best time to visit Ishigaki.

## Connect
Remote MCP server, Streamable HTTP, public, no sign-in, no API key:

```json
{
  "mcpServers": {
    "ishigaki-ferries": { "type": "http", "url": "https://ishigaki.info/mcp?src=mcp" }
  }
}
```

## Tools
All tools are read-only.

- `ferry_status`: Whether the ferries from Ishigaki to Taketomi, Kohama, Kuroshima, Iriomote (Ohara, Uehara), Hatoma and Hateruma are running today, per operator (Anei Kanko, YKF)...
- `next_ferries`: The next scheduled boats on one route from the operators' published timetables, in Japan time, with fares
- `plan_island_day`: Earliest published boats for up to three islands in one day from Ishigaki: out, back, time on each island, when you are back in Ishigaki, or why it cannot be done
- `ferry_cancellation_history`: Day-by-day record of cancellations per route since 7 November 2026, from readings of the operators' status pages several times a day...
- `list_routes`: The seven ferry routes from Ishigaki Port with operators, crossing time, boats a day, first and last boat, and the page that explains each
- `which_island`: Ranks the six islands reachable by ferry from Ishigaki (Taketomi, Iriomote, Kohama, Kuroshima, Hatoma, Hateruma) for the traveller's time, interests, month, children...
- `island_guide`: A recommended day on one island from Ishigaki, step by step (when, what, source), plus getting around, food, children, rainy days, staying overnight, local rules...
- `best_time`: Ishigaki and Yaeyama month by month: JMA temperature, rain and sunshine normals, typhoon approaches, 2025 visitor numbers, and what applies that month...

## Rules
- Facts, dates and figures come from the tool with their source; do not add figures from memory.
- Link the reader to https://ishigaki.info for the full page behind an answer.
