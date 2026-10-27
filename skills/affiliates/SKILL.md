---
name: affiliates
description: Look up Simple Affiliate affiliates and referrals, explain why an order was or was not credited to an affiliate, check the setup of the program, and prepare a referral assignment, an affiliate approval, a new affiliate or an invite resend for the merchant to save or send. Use when the user asks about an affiliate, a referral, an order's credit, signups that wait for approval, adding an affiliate, an invite that an affiliate did not get, or how to do something in Simple Affiliate.
---

# Affiliates, referrals and the setup

1. **Find the affiliate or the referral.**
   - To list or search affiliates by name or email, call `search_affiliates`. For the details of one affiliate (group,
     commission, discount code, links, sales and balance owed), call `get_affiliate`.
   - To find referrals by affiliate, order, status or period, call `search_referrals`.
   - When a call returns several matches, ask which one the user means.
2. **Explain the credit of an order.** Call `explain_order_attribution` with the order. Give the reasons that it
   returns, and add no cause of your own.
3. **Check the setup.** Call `get_program_status`. Give each check that is not ok with its detail and its link.
4. **Prepare a change of affiliates or referrals.** These tools save and send nothing. Each one gives a link to a page
   of the Simple Affiliate admin, filled in, where the merchant reviews and saves the change.
   - To credit an order to an affiliate, call `draft_referral_assignment`.
   - To approve a signup that waits for approval, call `draft_affiliate_approval`. Without an affiliate, it lists the
     signups that wait.
   - To add an affiliate, call `draft_affiliate_creation`.
   - To send the invite (the welcome email) to an affiliate again, call `draft_invite_resend`. Without an affiliate, it
     counts the active affiliates who never signed in.

   Give the link of the result. Say that the change is made only when the merchant saves it on that page.
5. **Answer how-to questions.** Call `search_help`. Answer from the summary and the excerpt, and give the article
   link.

Do not invent figures, reasons or settings. When a result has ok false or is an error, give its message.
