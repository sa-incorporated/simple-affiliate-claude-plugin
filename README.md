# Simple Affiliate for Claude

Run the affiliate program of your Shopify store from Claude. [Simple Affiliate](https://simple-affiliate.com) is the
affiliate program app for Shopify stores. This plugin connects Claude to your Simple Affiliate account. With it, you
can:

- see the Overview page, the Analytics overview and the Sales, Sales (legacy), Products sold, Link tracking and
  Payouts reports;
- look up affiliates and referrals, and find out why an order was or was not credited to an affiliate;
- see what you owe your affiliates, and the payout settings;
- check the setup of the program and the setup checklist;
- read the settings of each settings tab, the affiliate groups, the product commissions, the linked stores and the
  headless storefront;
- change the Emails, Signup, Referral, Dashboard, Translations and Klaviyo settings, the group automation flow, the
  affiliate groups, the product commissions, the linked stores and the headless storefront, after you confirm;
- prepare a referral assignment, an affiliate approval or a new affiliate, which you save in the Simple Affiliate admin.

## What you need

- A Shopify store with [Simple Affiliate](https://apps.shopify.com/simple-affiliate) installed. The plugin works on
  every Simple Affiliate plan. As in the admin, some reports and settings need a paid plan or a higher plan, and
  Claude tells you when the plan of your store does not include one.
- A staff account on that store. You connect as yourself, on one store.
- Claude on the web, the Claude desktop or mobile app, Cowork, or Claude Code.

## What the plugin contains

- **One connector**, `simple-affiliate`: the remote MCP server `https://mcp.simple-affiliate.com/mcp`, which SA Inc.
  operates. You sign in with OAuth. The plugin holds no key and no password.
- **Four skills** that tell Claude how to use the connector:
  - `get-started` checks the connection and shows what to ask.
  - `reports` reads the Overview page, the Analytics overview, the reports and what you owe your affiliates.
  - `affiliates` looks up affiliates and referrals, explains the referral of an order, and prepares a referral, an
    approval or a new affiliate for you to save in the admin.
  - `settings` reads the settings, the groups, the product commissions, the linked stores and the headless
    storefront, and changes them after you confirm.

The plugin has no hooks, no scripts and no local programs. It runs nothing on your computer, and it sends data only to
`mcp.simple-affiliate.com`.

## Connect

1. Add the Simple Affiliate plugin to Claude. In Claude Code, run these two commands:

   ```text
   /plugin marketplace add sa-incorporated/simple-affiliate-claude-plugin
   /plugin install simple-affiliate@simple-affiliate
   ```

2. Connect the Simple Affiliate connector. On claude.ai and in the desktop app, open the plugin's **Connectors** tab.
   In Claude Code, run `/mcp`, choose `simple-affiliate` and sign in.
3. Type the address of your store, for example `your-store.myshopify.com`.
4. Approve the connection in your Shopify admin. The page shows the assistant and the store.
5. Ask Claude: "Help me get started with Simple Affiliate."

## What you can ask

- "Is my affiliate program set up correctly?"
- "How did my affiliates do in the last 90 days?"
- "What do I owe my affiliates, and who can't be paid?"
- "Why was order 1001 not credited to an affiliate?"
- "Raise the commission of the VIP group to 15%."
- "Show the Products sold report for the last 90 days."

## You confirm before a setting changes

Claude cannot change a setting by itself. When you ask it for a change, Simple Affiliate shows the change in a
Confirm card in the conversation. Nothing changes until you click **Confirm**.
A card that you do not confirm expires after 10 minutes.

Claude also cannot add an affiliate, approve a signup or assign a referral. It prepares them: it gives you a link to
the page of the Simple Affiliate admin, filled in, and you review and save it there.

## No money moves from Claude

Claude cannot pay an affiliate, start a payout or change the payout settings. It shows what you owe and the payout
settings, and you make the payouts in the Simple Affiliate admin.

## Where the Confirm card shows

The Confirm card shows in Claude on the web and in the Claude apps. Claude Code in a terminal cannot show the card.
There, you make the change in the Simple Affiliate admin.

## Privacy and data

Simple Affiliate returns only data that its admin shows you, for the store that you connected. It never returns your
Klaviyo key, a pairing code of a store link, or the bank or payout account of an affiliate. Claude receives the
affiliate program data that you ask for. The [privacy policy](https://simple-affiliate.com/pages/privacy-policy) tells
how Simple Affiliate uses data.

## Disconnect

- In Simple Affiliate, open **Settings**, then the **Integrations** tab. Under **AI assistant connections**, click
  **Revoke**.
- Or disconnect the connector in Claude.
- If you uninstall Simple Affiliate from the store, every connection stops.

## Support

Write to us from <https://simple-affiliate.com/pages/contact>. The
[terms of service](https://simple-affiliate.com/pages/terms-and-conditions) apply to the use of Simple Affiliate.
