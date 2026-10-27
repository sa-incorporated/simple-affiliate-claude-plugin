---
name: reports
description: Read the results of a Simple Affiliate program - the Overview page, the Analytics overview, the sales of linked stores, the Sales, Sales (legacy), Products sold, Link tracking and Payouts reports, the performance of affiliates over a period, and what the store owes its affiliates. Use when the user asks how the program or an affiliate performed, for a report, for top affiliates or products, or about payouts and balances owed.
---

# Read the results of the affiliate program

Each tool gives a page or a report as the Simple Affiliate admin shows it. Give the figures as the tool returns them,
with their currency. Do not add, convert or estimate amounts, and do not add the rows of a report to get a total.

1. **Choose the tool.**
   - A short summary of a period, compared with the period before, with the top affiliates:
     `get_performance_summary`.
   - The Overview page: `get_overview`. The setup checklist of that page: `get_onboarding_checklist`.
   - The Analytics overview: `get_analytics_overview`. The sales of this store and of its linked stores:
     `get_linked_store_sales`.
   - One row for each affiliate: `get_affiliate_sales_report` (the Sales report). Sales by day, week, month or
     quarter: `get_sales_report` (the Sales (legacy) report).
   - Products sold through referrals: `get_products_sold_report`. Referral links with clicks and conversion:
     `get_link_tracking_report`.
   - What the store owes, the next payout and the affiliates who cannot be paid: `get_payout_summary`. One row for
     each affiliate with the payout method, the paid amount and the balance: `get_payouts_report`.
2. **Give the period.** Use the period that the user names. When they name none, the tool uses its default period:
   say which period the result covers. The Link tracking and Payouts reports have no period.
3. **Read all the rows that the user needs.** A report gives one page of rows. When hasNextPage is true and the user
   needs more rows, call the report again with the next page.
4. **Answer.** Give the totals as the report returns them. Name the top rows that the question is about, and say when
   a result has no rows.

When a tool says that the plan of the store does not include it, or that it is not available, tell the user, and do
not give figures from another report in its place. No tool starts a payout: the user makes payouts in the Simple Affiliate admin.
