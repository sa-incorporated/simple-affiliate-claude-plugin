---
name: settings
description: Read and change the settings of Simple Affiliate - the Payout, Signup, Referral, Email settings, Email templates, Dashboard, Translations, Integrations (Klaviyo) and Billing tabs, the design of the storefront signup page, the group automation flow, the Order tags and Customer tags flows, the affiliate groups and their product and collection commissions, the linked stores, the headless storefront, the affiliate links of the store menus and test emails. Use when the user asks what a setting is, or asks to change a setting, a group, a commission or the group automation flow.
---

# Read and change the settings

## Read

- A settings tab: `get_payout_settings`, `get_signup_settings`, `get_referral_settings`, `get_email_settings`,
  `get_dashboard_settings`, `get_translation_settings` or `get_klaviyo_settings`. The plan and its limits:
  `get_billing_plan`.
- The groups: `list_groups`. The product and collection commissions of one group: `get_group_commissions`.
- The group automation flow: `get_group_automation_flow`.
- The Order tags and Customer tags flows (the Shopify tags that Simple Affiliate writes): `get_tag_flows`. No tool
  changes them: the merchant changes them in the Simple Affiliate admin.
- The linked stores: `get_store_link`. The headless storefront: `get_headless_storefront`.
- The design of the storefront signup page: `get_signup_page_design`. It gives the page URL, each setting of the
  Affiliate Signup block with its limits, the Custom CSS of its section and the CSS classes of the form.
- The store menus and their affiliate links: `get_store_menus`.

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
     `set_vercel_cookie_purpose` or `disconnect_vercel`;
   - the design of the storefront signup page: `update_signup_page_design`. A missing signup page, template or
     block: `repair_signup_page`;
   - a link to the affiliate dashboard or the signup page in a store menu: `add_affiliate_page_to_menu`;
   - a test of an affiliate email to the store account email: `send_test_email`.

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

## Design the signup page

The signup page design tools show only for a store on new customer accounts with a plan that includes the custom
signup form (Pro or above). When they do not show, tell the user that the plan or the customer accounts of the store
do not include the custom signup page; `get_billing_plan` gives the plan. When they show but refuse, give the reason
of the refusal: for example the custom signup form is off (`update_signup_settings`), or the store has a headless
storefront.

To make the signup page match the store, open the page URL and two other pages of the store, and note their fonts,
colors, spacing, input and button shapes. Use the block settings first: width, padding, alignment, sizes and colors,
the input border and background colors included. The "Dark mode" colors of the block apply only when the device of the
shopper is in dark mode (prefers-color-scheme), and a blank dark color keeps the light color. When the dark mode of the
store follows the device, check the page with the device in dark mode too, and set these colors. When the store has a
dark mode switch on the page instead, do not set them: use the color variables of the theme in the Custom CSS, or tell
the user that the block colors follow only the device. Use the Custom CSS of the section only for what no setting changes,
such as the heading font or the border width and radius of the inputs. The section_custom_css input replaces the
whole Custom CSS of the section: start from `customCss.value` of `get_signup_page_design`, keep the rules that the user did not ask
to change, remove each CSS comment, and keep the total at 500 characters or fewer. Make one
`update_signup_page_design` preview with all the changes.

When a signup page tool says that the page, its template or its Affiliate Signup block is missing, make a
`repair_signup_page` preview. After the Confirm, read the design again: a new template has the default design.

## Store menus and test emails

To add the affiliate dashboard or the signup page to a menu of the store, such as the footer, read the menus with
`get_store_menus`, then make an `add_affiliate_page_to_menu` preview with the handle of the menu. The link goes at the
end of the top level of the menu, and the other links stay.

After a change of the email design or of an email text, offer `send_test_email`. The test goes only to the email
address of the store account, which the card shows, and the store can send 20 tests a day.
