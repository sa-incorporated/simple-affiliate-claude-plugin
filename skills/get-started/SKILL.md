---
name: get-started
description: Check the Simple Affiliate connection, name the connected Shopify store, and show what to ask. Use when the user has just added Simple Affiliate, asks how to get started or what Simple Affiliate can do here, or when a Simple Affiliate tool is missing or fails because the connector is not connected.
---

# Get started with Simple Affiliate

Simple Affiliate runs the affiliate program of a Shopify store: affiliates, groups, referrals, commissions and
payouts. The connector acts as the staff member who connected it, on one store only.

1. Check the connection by calling `get_program_status` with `{}`.
   - If the Simple Affiliate tools are missing, or the call fails because nobody is signed in, tell the user to
     connect the Simple Affiliate connector, and stop. On claude.ai and in the desktop app, they connect it on the
     plugin's Connectors tab. In Claude Code, they run `/mcp`, choose the Simple Affiliate server and sign in.
   - Sign-in asks for the store's `myshopify.com` address, then for approval in that store's Shopify admin. The store
     needs Simple Affiliate installed from the Shopify App Store.
2. Name the connected store. The server's instructions say which store this connection reached ("Connected to Simple
   Affiliate for the store …"). Say it in one short sentence. If a check of the result has the status action_needed,
   name it in one line with its link.
3. Offer three things they can ask, one line each:
   - "How did my affiliates do in the last 90 days?"
   - "What do I owe my affiliates, and who can't be paid?"
   - "Raise the commission of the VIP group to 15%."
4. Explain in two sentences. First: each change in Simple Affiliate happens only after they click Confirm in the card
   that appears. Second: Claude does not pay affiliates or change the payout settings, and
   it prepares a new affiliate, an approval or a referral as a link that they save in the Simple Affiliate admin.

Keep it short. If the user added the plugin in the middle of a task, continue that task in the same conversation.
Never list the affiliates or their data during setup.
