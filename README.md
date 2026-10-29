# DSers Dropshipping Automation for Claude

Connect your favorite AI client to DSers and move from product discovery to listings, store operations, orders, fulfillment, and delivery tracking — all in one conversation.

This is the DSers plugin for Claude. It connects Claude to [DSers MCP](#dsers-mcp) and adds skills for the daily work of a dropship store: finding products and suppliers, cleaning up and publishing listings, checking profit and pricing rules, keeping supplier mapping working, placing supplier orders, and tracking parcels.

Before Claude changes anything in DSers or in your store, it shows what will change and waits for you to agree in the chat.

## What's included

- **DSers MCP**: a connection to `https://ai.dsers.com/mcp`, the same server as the [DSers connector in the Claude directory](https://claude.ai/directory/dsers). You sign in to DSers with OAuth.
- **Skills**:

| Skill | What it helps with |
| --- | --- |
| account-and-stores | Getting started, connected stores and supplier accounts, reconnecting a store, plan, AI Credits, invoices |
| product-sourcing | Product ideas, supplier search by keyword or image, comparing cost, stock, and shipping, adding products to the Import List |
| listing-editing | Cleaning up imported titles, descriptions, variants, and images, prices before publishing, collections and tags |
| product-publishing | Publishing Import List products to your stores with the shipping and publish settings you choose |
| profit-and-pricing | Profit per order and product after fees and ads, pricing rules, store-wide and single-product price changes |
| supplier-mapping | Linking store products to suppliers, backup suppliers, suppliers by country, bundles, AI Mapping, supplier changes |
| order-fulfillment | Why orders are stuck, fixing addresses and shipping methods, placing orders with suppliers, payment links |
| package-tracking | Parcel status, delivery exceptions, sending tracking to your store, buyer notifications, delivery disputes |

Claude picks the skill that fits your request.

## Try it

- "Place today's orders."
- "Find a supplier for this phone stand that ships to the US in under 10 days."
- "Clean up the titles of the products in my Import List."
- "Am I making money this month?"
- "Which of my products have no supplier?"
- "Why can't I place order 1052?"
- "Which parcels are stuck?"

## Install

**Claude (web, desktop, and Cowork)**: once the plugin is listed in the Claude directory, open Customize → Plugins, search for DSers, and add it. Then connect DSers from the plugin's Connectors tab and sign in to DSers. On Team and Enterprise plans, an owner may need to add the plugin for the organization first.

**Claude Code**

```text
/plugin install dsers-dropshipping-automation --marketplace dsers/claude-dsers-plugin
```

On Claude Code versions before 2.1.275, add the marketplace first:

```text
/plugin marketplace add dsers/claude-dsers-plugin
/plugin install dsers-dropshipping-automation@claude-dsers-plugin
```

Then run `/mcp`, select the DSers server, and sign in to DSers in the browser window that opens.

You never paste a password or API key into Claude. Check the connection with a read-only request:

> Show my DSers plan and list my connected stores. Do not make any changes.

## Requirements

- A DSers account. [Sign up](https://accounts.dsers.com/accounts/register?utm_source=claude_plugin&utm_medium=ai_assistant&utm_campaign=dsers_plugin&utm_content=readme)
- A DSers Advanced, Pro, or Enterprise plan. These plans include MCP Connection; Basic does not ([DSers MCP documentation](https://www.dsers.com/en/mcp-server), [DSers pricing page](https://www.dsers.com/pricing)).
- At least one Shopify or Wix store connected in DSers, for tasks that touch your store.

## Stores and suppliers

From the [DSers integrations page](https://www.dsers.com/en/integration):

- **Sales channels**: DSers supports Shopify, Wix, WooCommerce, eBay, TikTok Shop, Amazon, Walmart, Big Cartel, Jumpseller, Cartpanda, Square, Ecwid, BigCommerce, Squarespace, SHOPLINE, LPQV, Magento, Genstore.ai, and CSV workflows. Check the channel list inside DSers for the latest availability.
- **Sourcing**: DSers supports sourcing workflows for AliExpress, Alibaba.com, 1688, and the DSers Verified Agent Network.

DSers MCP needs at least one Shopify or Wix store connected in DSers ([DSers MCP documentation](https://www.dsers.com/en/mcp-server)).

## About DSers

DSers is an ecommerce platform founded in 2018 that helps sellers spend less time on repetitive operations and more time building their business — supporting dropshipping and wholesale through connected sourcing, automation, and fulfillment workflows. As an official Alibaba Group partner, DSers supports 10M+ dropshippers, with 100M+ SKUs in the product pool and 300M+ orders processed. DSers supports sourcing across AliExpress, 1688.com, Alibaba.com, and the DSers Agent Network, giving sellers transparent options as their sourcing needs evolve.

Technology should understand more, automate more, and stay dependable—so people can focus on judgment, creativity, relationships, and growth. [More about DSers](https://www.dsers.com/en/about-us)

## DSers MCP

DSers MCP is the official MCP server from DSers for AI-powered dropshipping automation. Connect Claude to DSers and move from product discovery to listings, store operations, orders, fulfillment, and delivery tracking — all in one conversation.

What you can do with DSers MCP:

- **Discover products and logistics**: Search by keyword or image, inspect supplier products, compare logistics by country, and monitor supplier-product changes.
- **Build and optimize import drafts**: Create import-list products, then edit content, images, options, variants, prices, organization, and categories before launch.
- **Configure stores and publish**: Connect or reauthorize stores, create Shopify shipping profiles, resolve logistics choices, and publish through tracked jobs.
- **Operate catalogs and mappings**: Inspect live products, update price or stock, import store products, and manage Basic, Advanced, or AI-assisted supplier mappings.
- **Run orders and supplier fulfillment**: Validate addresses, update order details, and place or cancel supplier orders.
- **Control tracking and buyer updates**: Inspect package events, refresh supplier tracking, synchronize or replace store tracking numbers, and send buyer notifications.

DSers MCP works alongside the DSers dashboard. [DSers MCP documentation](https://www.dsers.com/en/mcp-server)

## Data, network, and approvals

- The plugin contains skills and a connection to `https://ai.dsers.com/mcp`. It has no scripts, hooks, agents, or background processes.
- When DSers is connected, Claude sends requests to DSers under your DSers sign-in, and DSers processes that data under its [privacy policy](https://www.dsers.com/en/privacy).
- DSers tools include write operations: placing supplier orders, which spends money through your DSers account; changing prices; and publishing listings. The skills ask for your agreement in the chat before each change, and Claude's own tool permission prompts still apply.

## Troubleshooting

- **No DSers tools**: in Claude Code, run `/mcp` and check that the DSers server is connected; sign in if it asks. In the Claude apps, check that DSers is connected under Customize → Connectors.
- **Plan or permission errors**: Claude reports the message DSers returns. If it says your plan does not include MCP Connection, see the [DSers pricing page](https://www.dsers.com/pricing).
- **Wrong DSers account**: disconnect DSers, sign out of DSers in the browser, then connect again and sign in with the account you want.

## Remove

- **Claude Code**: `/plugin uninstall dsers-dropshipping-automation@claude-dsers-plugin`
- **Claude apps**: remove the plugin under Customize → Plugins and disconnect DSers under Customize → Connectors.

## Support

- DSers account, plan, and DSers MCP questions: [DSers Help Center](https://help.dsers.com/) or support@dserspro.com
- Plugin issues: [GitHub Issues](https://github.com/dsers/claude-dsers-plugin/issues)

## License

[MIT](LICENSE)
