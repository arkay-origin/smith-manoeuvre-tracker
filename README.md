# The Conversion Ledger — Smith Manoeuvre Tracker

A free, single-file tracker for the Smith Manoeuvre and Canadian leveraged-investing bookkeeping.

**▶ [Use it here](https://arkay-origin.github.io/smith-manoeuvre-tracker/)** — no signup, no account, nothing to install.

---

## Privacy

Everything runs in your browser. There is no server, no account, no cloud, no cookies, no analytics, no tracking of any kind.

Your data is saved to a JSON file **on your own machine**. You load it when you start and save when you finish. Nothing you type is ever transmitted anywhere.

Auto-save is optional and off by default. Turn it on and the tool writes changes straight to your linked file — it stays off until you explicitly enable it, and the setting is remembered in your data file. It needs the File System Access API, so it works in Chrome and Edge, in Brave once you enable the flag at `brave://flags`, and not in Firefox or Safari. Everywhere else, Save and Load work exactly the same, just manually.

Save As writes a separate copy and re-links to it, so you can keep dated snapshots without duplicating files by hand. The linked filename shows in the sidebar.

You can also just download `index.html` and run it offline. It works exactly the same.

---

## How to use it

**First-time setup**, in this order:

1. **Mortgage** — principal, rate, compounding basis, start date. Compounding is required and has no default: semi-annual for most Canadian fixed mortgages, often monthly on variable. Your documents state it.
2. **HELOC** — add your line with its rate basis and credit limit. If your room grows as you repay principal, choose a re-advanceable limit type.
3. **Property (rental / second home)**
- Track a mortgage on another property with its own amortization and interest per year
- Record income and expenses line by line, split into current and capital
- Ownership share applied throughout, for jointly-owned property
- Kept out of the debt-conversion figures: rental interest is already deductible, so it isn't a conversion target
- Record-keeping only — no capital cost allowance, no T776, and no judgement about what's deductible

**Tax** — set your marginal rate so deductible interest and refund estimates work.

**Each month:** record the prepayment on Mortgage, then the matching draw on HELOC tagged Investment — that offers the purchase dialog so the buy lands in the ledger linked to the draw. Prepay, re-borrow, invest.

**At tax time:** the Tax tab totals deductible interest per year per line for Line 22100 and estimates the refund. Reconcile against your lender's statements before filing. Record where the refund went, then print the audit package and keep your statements behind it.

Backfilling history? Enter events with their real dates in any order — the schedule and the ledger replay from dates, not entry order.

Not sure the strategy suits you? The Simulator answers that before you commit to any bookkeeping.

---

## What it does

**Mortgage**
- Canadian semi-annual compounding — plus monthly, payment-cycle-matched, annual, quarterly, and daily
- Monthly / bi-weekly / accelerated bi-weekly / weekly / accelerated weekly payments
- Payment frequency changes mid-mortgage (history before the change stays accurate)
- Custom payment amounts, and dated payment changes
- Rate changes and renewals, including a change of compounding basis at renewal
- Trigger rate and negative-amortization warnings
- Prepayments tagged by source, with notes
- Payoff date, time remaining, and time saved vs. the original amortization
- Yearly summary or full per-payment schedule, CSV export
- Metrics and prepayments up front; the set-once configuration tucked into a collapsible section

**HELOC**
- Multiple credit lines for multi-lender setups
- Draws tagged by purpose — investment principal and capitalized interest kept separate
- Fixed rate history, or prime + delta with a shared prime timeline
- Fixed credit limit, or re-advanceable room that grows as mortgage principal is repaid
- Mixed-use contamination warnings

**Investments**
- CRA average-cost ACB engine
- Buys, sells, dividends, DRIP, return of capital, phantom distributions
- Stock splits — forward and reverse, with fractional handling (keep, round down, or cash in lieu)
- Opening positions: carry in units and ACB from records you already keep, and track forward from there
- CSV import (Wealthsimple auto-maps; others via manual column mapping)
- Superficial loss flagging
- Record interest charged in cash so Line 22100 comes from your statements rather than an estimate
- Ledger grouped by symbol, with open positions separated from past holdings
- Per-event detail: open any transaction to see before → change → after with a plain-English explanation
- All amounts are treated as Canadian dollars — there is no currency conversion, so convert foreign trades before entering them

**Tax**
- Deductible interest per year, per line, accrued daily across rate changes
- Refund estimate at your marginal rate (Line 22100)
- Refund deployment tracking, with optional auto-creation of the matching prepayment, HELOC payment, or investment purchase
- T1213 draft worksheet

**Simulator**
- Quick check: your break-even return, with a market-return sensitivity sweep
- Full projection: do nothing vs. debt swap vs. leveraged SM, side by side
- Optional margin-on-HELOC overlay with an explicit helps / hurts / no-difference verdict

**Dashboard and audit**
- Debt conversion percentage, non-deductible → deductible
- Light mode (annual statement totals) or Full mode (per-transaction), with the net-position chart plotted in either
- Printable audit package, Schedule 3 disposition support, full JSON export
- Record-keeping guide covering capitalized interest, ROC, mixed use, and superficial loss
- Light and dark themes

---

## Important

**This is an educational tool. It is not financial, tax, legal, or investment advice.**

The Property tab is record-keeping, not tax computation. It totals what you recorded; it does not decide what's deductible, does not model capital cost allowance, and does not produce a T776. Rental interest and expenses belong on T776 against rental income — a separate stream from the Line 22100 investment interest the rest of the tool tracks. The two are never combined.

The Smith Manoeuvre is leveraged investing and carries a real risk of loss. Interest deductibility depends on facts this tool cannot verify.

Interest figures here are **estimates** using simple daily accrual on the tagged deductible balance, with mixed-line payments split pro-rata. **Your lender's statements govern.** Reconcile against them, and consult a CPA, before filing anything.

The tool deliberately has no default values for tax rate or compounding basis — those depend on your province, income, and mortgage documents, and a plausible-looking wrong number is worse than a blank field.

---

## Feedback

Built for the r/smithmanoeuvre community and shaped by their suggestions. Issues and feature requests are welcome.

---

## Changelog

Dates are build dates; the live site always serves the newest.

**2026-08-09** — Record HELOC interest charged and paid in cash as its own entry: it doesn't touch the balance, and the Tax tab then reports your statement figure for Line 22100 instead of the tool's accrual estimate, showing both side by side so a gap is visible. Interest is prorated by each line's deductible share. CSV import remembers the newest transaction it brought in, so you know where to export from next time. Date columns on the entry tables sort both ways, newest first by default — display only; the engines always compute in true date order. Opening position moved to the end of the transaction type list so Buy stays the default.

**2026-08-08** — New Property tab for rentals and second homes: a mortgage with its own schedule and yearly interest, line-by-line income and expenses split into current and capital, and an ownership-share setting for jointly-owned property. Deliberately record-keeping rather than tax computation — no CCA, no T776, and rental figures are kept separate from Line 22100 investment interest throughout, including in the audit package. HELOC lines can now record which property secures them; lines on another property keep working normally for investment draws but can't use the growing-room limit types, which derive from the principal-residence mortgage.

**2026-08-07** — Opening positions: enter units and ACB carried in from another tracker or your accountant and track forward, with explicit notes on what that means for realized-gain coverage, superficial-loss detection, and deductibility tracing. Save As with re-linking, and the linked filename now shows in the sidebar. Investment ledger defaults to grouping by symbol, summarises each holding in its header, separates past holdings, and links symbols to their section. Simulator re-runs automatically when inputs change, and explains what extra and freed cashflow actually do. Stated plainly that all amounts are treated as Canadian dollars. Edit and delete controls aligned across every table.

**2026-08-04** — Guided setup for new users and a "Using this tool" walkthrough. HELOC lines reorganised so metrics and entry come first, setup collapses once configured. Full amortization schedule renders a window with an expander instead of every row. Accessibility pass: current-tab state, labelled controls, better light-mode contrast. Build number added.

**2026-08-02** — Simulator rebuilt on an equal-cash principle: every strategy deploys the same out-of-pocket cash each month, so none is penalised for paying off sooner. Fixes three defects that made the debt swap look worse than doing nothing. Results now report mortgage-free date, time saved, and net position at each strategy's own payoff. New setting for what freed cashflow does after payoff. Entries can be edited in place across prepayments, HELOC transactions, and the investment ledger.

**2026-08-01** — Re-advanceable HELOC limits: derive from home value and LTV, or track a sub-account's opening room plus its share of principal repaid. Draws warn when they exceed available room. Investment ledger shows each transaction's source and links both ways, with cascading deletes. Live totals in the transaction dialog. Printable audit package pagination fixed.

**2026-07-31** — Light and dark themes. Break-even quick check in the Simulator. Per-event detail drawer showing before, change and after for every transaction. Payment frequency changes mid-mortgage. Time remaining and time saved metrics.

---

## Support

This tool is free and always will be — no ads, no accounts, no tracking, no paywall.

If it saved you time, you can [buy me a coffee](https://buymeacoffee.com/a50443536g). Entirely optional.

Note: the donation link is a plain hyperlink. No third-party widget or script is embedded, so nothing loads from outside this page and nothing about your visit is reported anywhere.

---

## License

Licensed under the **GNU General Public License v3.0** — see [LICENSE](LICENSE).

You are free to use, study, modify, and share this tool. If you distribute a modified version, it must also be released under the GPL with its source available, so improvements stay open.

The copyright holder reserves the right to distribute their own versions of this work under different terms, including commercially.
