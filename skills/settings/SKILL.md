---
name: settings
description: Read and change the settings of Simple Affiliate - the Payout, Signup, Referral, Emails, Dashboard, Translations, Integrations (Klaviyo) and Billing tabs, the group automation flow, the affiliate groups and their product and collection commissions, the linked stores and the headless storefront. Use when the user asks what a setting is, or asks to change a setting, a group, a commission or the group automation flow.
---

# Read and change the settings

## Read

- A settings tab: `get_payout_settings`, `get_signup_settings`, `get_referral_settings`, `get_email_settings`,
  `get_dashboard_settings`, `get_translation_settings` or `get_klaviyo_settings`. The plan and its limits:
  `get_billing_plan`.
- The groups: `list_groups`. The product and collection commissions of one group: `get_group_commissions`.
- The group automation flow: `get_group_automation_flow`.
- The linked stores: `get_store_link`. The headless storefront: `get_headless_storefront`.

Give each setting with its value as the result gives it. When lockedSettings names a setting, say that it has no
effect for this store and what it needs.

## Change

1. **Read first.** Read the tab or the group before a change, so that you use the current values and the right group
   id.
2. **Make the preview.** Call the tool of the change with only the settings that the user asks to change:
   - a settings tab: `update_email_settings`, `update_signup_settings`, `update_referral_settings`,
     `update_dashboard_settings`, `update_translation_settings` or `update_klaviyo_settings`;
   - the group automation flow: `update_group_automation_flow`;
   - a group: `update_group`, `create_group` or `delete_group`;
   - the commissions of products and collections in a group: `set_product_commissions` or
     `remove_product_commissions`;
   - the linked stores: `update_store_link_group_map` or `remove_store_link`;
   - the headless storefront: `set_headless_storefront_host`, `clear_headless_storefront_host`,
     `set_vercel_cookie_purpose` or `disconnect_vercel`.

   The call saves nothing. It shows a Confirm card with the changes. When the call refuses the change, give its reason.
3. **Stop and let the user confirm.** Tell the user to read the card and click Confirm or Cancel. Do not call the tool
   again to confirm, and do not say that the change is saved until the card or a later read shows it. A card expires
   after 10 minutes. When a Confirm fails because a setting changed after the preview, read the setting again before
   you make a new preview.
4. **One change for each request.** Make a change only when the user asks for it. When the user asks for changes of
   several tabs, groups or stores, make one preview for each, and each one needs its own click.

The payout settings, the payout methods and the plan do not change from Claude: give the user the Simple Affiliate
admin for them. If no Confirm card shows, for example in Claude Code in a terminal, the user makes the change in the
Simple Affiliate admin.
