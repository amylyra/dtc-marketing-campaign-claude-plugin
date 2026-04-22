# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool the user connects in that category. For example, `~~email marketing` might mean Klaviyo, Mailchimp, or any other email platform with an MCP server.

Plugins are **tool-agnostic** — they describe workflows in terms of categories (design, SEO, email marketing, etc.) rather than specific products. The `.mcp.json` pre-configures specific MCP servers, but any MCP server in that category works.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|----------|-------------|-----------------|---------------|
| Chat | `~~chat` | Slack | Microsoft Teams |
| Design | `~~design` | Canva, Figma | Adobe Creative Cloud |
| Email marketing | `~~email marketing` | Klaviyo | Mailchimp, Brevo, Customer.io |
| SEO | `~~SEO` | Ahrefs, Similarweb | Semrush, Moz |
| Marketing analytics | `~~marketing analytics` | Supermetrics | Google Analytics, Triple Whale |
| Product analytics | `~~product analytics` | Amplitude | Mixpanel, Google Analytics |
| Knowledge base | `~~knowledge base` | Notion | Confluence, Guru |
| Storefront | `~~storefront` | — | Shopify, WooCommerce, BigCommerce |
| Ad platform | `~~ad platform` | — | Meta Ads, Google Ads, TikTok Ads |
| Attribution | `~~attribution` | — | Triple Whale, Northbeam, Rockerbox |
| Reviews | `~~reviews` | — | Stamped, Judge.me, Yotpo, Okendo |

## Not yet configured

The following categories don't have pre-configured MCP servers in `.mcp.json` but are referenced by skills. When MCP servers become available for these tools, add them to `.mcp.json` and skills will automatically use them:

- **Storefront** — product catalog, inventory, order data. Skills reference `~~storefront` for product page updates and inventory checks.
- **Ad platform** — campaign data, creative performance, audience insights. Skills reference `~~ad platform` for paid acquisition reporting and competitive ad research.
- **Attribution** — cross-channel attribution, incrementality testing. Skills reference `~~attribution` for blended MER and contribution margin analysis.
- **Reviews** — customer reviews, ratings, UGC. Skills reference `~~reviews` for social proof content and customer voice data.
