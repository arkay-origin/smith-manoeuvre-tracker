# The Conversion Ledger — Smith Manoeuvre Tracker

A free, single-file tracker for the Smith Manoeuvre and Canadian leveraged-investing bookkeeping.

**▶ [Use it here](https://arkay-origin.github.io/smith-manoeuvre-tracker/)** — no signup, no account, nothing to install.

---

## Privacy

Everything runs in your browser. There is no server, no account, no cloud, no cookies, no analytics, no tracking of any kind.

Your data is saved to a JSON file **on your own machine**. You load it when you start and save when you finish — on Chrome and Edge it can auto-save to the linked file so you don't have to think about it. Nothing you type is ever transmitted anywhere.

You can also just download `index.html` and run it offline. It works exactly the same.

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
- CSV import (Wealthsimple auto-maps; others via manual column mapping)
- Superficial loss flagging
- Per-event detail: open any transaction to see before → change → after with a plain-English explanation

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
- Light mode (annual statement totals) or Full mode (per-transaction)
- Printable audit package, Schedule 3 disposition support, full JSON export
- Record-keeping guide covering capitalized interest, ROC, mixed use, and superficial loss
- Light and dark themes

---

## Important

**This is an educational tool. It is not financial, tax, legal, or investment advice.**

The Smith Manoeuvre is leveraged investing and carries a real risk of loss. Interest deductibility depends on facts this tool cannot verify.

Interest figures here are **estimates** using simple daily accrual on the tagged deductible balance, with mixed-line payments split pro-rata. **Your lender's statements govern.** Reconcile against them, and consult a CPA, before filing anything.

The tool deliberately has no default values for tax rate or compounding basis — those depend on your province, income, and mortgage documents, and a plausible-looking wrong number is worse than a blank field.

---

## Feedback

Built for the r/smithmanoeuvre community and shaped by their suggestions. Issues and feature requests are welcome.

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
