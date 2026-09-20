# Campus Jobs Radar · 校招雷达

> China SOE (state-owned enterprise) campus recruitment, as structured data your AI can query.
> 让 Claude / Cursor 里的 AI 帮你盯国企央企校园招聘——查岗位、对专业、盯截止日。

**Live endpoint**: `https://mcp.xjradar.com/mcp` · **Landing page**: [xjradar.com](https://xjradar.com)

## Why

China's state-owned enterprises each publish campus recruitment announcements on their **own separate websites** — dozens of them, no unified entry. Graduates miss deadlines simply because no one can watch all the sites. This server turns those scattered announcements into a **single queryable database** for any MCP-capable AI assistant.

## What's inside

| | |
|---|---|
| **4,145** records indexed | jobs & recruitment programs |
| **24** official data sources | incl. China Resources 华润, iguopin 国聘, China Railway, China Mobile GD, China Southern Grid, China Post, Shenzhen Airport… |
| **1,500+** currently open | deadline-tracked |
| **Daily** refresh & re-verification | via automated crawlers |

Every record carries the **provenance triple**: original announcement URL + first-seen date + last-verified date. Fields the source didn't state are left empty — never guessed. No login-walled platforms, no personal data.

## Tools

| Tool | What it does |
|---|---|
| `search_jobs` | Filter by city, major, degree, graduate year, keywords; open-only by default |
| `list_deadlines` | What closes within the next N days — sorted countdown |
| `get_job_detail` | Full record: original major-requirement text, contracting entity, apply URL, source link |

## Quick start

Get a **free API key** (10 queries/day, never expires) by scanning the WeChat QR code on [xjradar.com](https://xjradar.com), then:

```json
{
  "mcpServers": {
    "campus-jobs-radar": {
      "url": "https://mcp.xjradar.com/mcp",
      "headers": { "X-API-Key": "YOUR_API_KEY" }
    }
  }
}
```

Claude Code: `claude mcp add --transport http campus-jobs-radar https://mcp.xjradar.com/mcp --header "X-API-Key: YOUR_API_KEY"`

Then just ask your AI in plain language:

- 「查 2027 届、深圳、还开放投递的国企岗位」
- "What SOE applications close in the next 14 days?"
- 「我是会计本科，筛出我能报的，标出最急的 3 个」

## Pricing

- **Free**: 10 queries/day, never expires, full data — no tricks.
- **Season Pass ¥29**: 500 queries/day through the current recruitment season (to 2026-11-30). See [xjradar.com](https://xjradar.com).

## Compliance

Data comes **only from official public channels** (corporate recruitment sites, government postings). This service is an index and reminder tool — always verify against the original announcement before applying. No personal information is collected. Crawler sources are public pages only, rate-limited, no login-wall circumvention.

## Links

- Landing page & docs: [xjradar.com](https://xjradar.com)
- Registry entry: `io.github.setozjl/campus-jobs-radar`
- Contact: via WeChat QR on the landing page

---

*Server source is maintained in a private repository. This public repo hosts the registry manifest ([server.json](server.json)) and documentation.*
