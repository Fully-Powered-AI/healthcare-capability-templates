# Clinic supply par levels and expiry check

From the clinic's own stock-count and usage exports, the person who orders supplies gets a par level and reorder point for every item in every room, what is below par, what will expire before it is used, and a draft order. Medical-surgical and office supplies only; a person approves every order.

*Capability template · Healthcare · Supply chain and inventory · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/clinic-supply-par-levels-and-expiry-check/)*

## The outcome

Every room in the clinic has a number for every item it stocks, worked out from what that room actually used rather than from habit. The par says how much the room should hold after each restock; the reorder point says when it cannot wait for the next order. Both show their arithmetic, so anyone can check a line with a calculator.

Short-dated stock stops being a surprise at the back of a drawer. The sheet takes each lot in date order and works out how much of it the room will use before its date, so the gauze that will be used in time is marked to use first and the kits that will not are counted, with what they cost.

The week ends with one draft order, grouped by supplier, that subtracts what is already on its way, rounds to the packs suppliers sell, and points out when another room holds spare stock of the same item. Nothing is ordered until the practice manager signs it.

Medicines, vaccines and controlled items are listed by name and left alone. They are for the person your practice names, never for this workflow.

## Who starts the work, and when

The person who orders supplies starts it straight after the regular stock count, before the order goes in: often the office manager or a medical assistant. It runs again when a room is added or rearranged, or when a supplier's delivery time changes.

The practice manager, or whoever the practice names, reads the draft order and approves, changes or holds it.

## What they supply

- **The stock count,** exported one row per lot per room, with expiry dates.
- **Usage for a recent period,** such as the last four weeks, by room and item.
- **The item list:** category, unit, pack size, unit cost, supplier and whether each item carries an expiry date.
- **The settings:** the days the clinic is open and closed, how often it orders, each supplier's delivery time, a buffer, the warning period for expiry and who approves orders.
- **Open orders and any stock-outs,** if there are any.

The column headers are checked first. If one does not match, the work stops and asks which column is which. Nothing connects to the clinic's systems; the person exports the files and supplies them.

## What comes out

One sheet in a fixed order, opening with what was read and what could not be assessed. Then the items to order now, every room's par and reorder point with its working, the items below par, the expired lots to take off the shelf, the lots that will not be used before their date, the lots to use first, and the draft order with an approval line. Items with no use in the period, items out of scope, things to check and rows that could not be assessed each have their own section, and an empty section says whether it was checked.

The sheet orders, moves and discards nothing, and it says so at the end.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the supply cupboard of a medical, dental or specialty practice, where exam and procedure rooms each keep their own stock.
- [Supply chain and inventory](https://fullypowered.ai/functions/supply-chain-and-inventory/): par levels, reorder points and earliest-date-first rotation applied room by room.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice whose pars were set years ago and live on shelf labels nobody has checked against use.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding rooms or providers, where last year's pars no longer match the week.

## What has to change for your company

Start with your own rooms and your own item list; the template supplies neither. Add your suppliers' delivery times, how often you order, and your closed days. Match the column names to what your systems export.

Several rules are our editorial choices, and the practice manager should confirm or change each: the par covers the days between orders, the delivery time and a two-day buffer; an item is treated as expired on its date; the warning period is 60 days; open orders are subtracted in full; spare stock in another room is shown and never subtracted; and only the med-surg and office categories are assessed. The complete list is in the template. Online stores should use [Inventory reorder plan](https://fullypowered.ai/capabilities/inventory-reorder-plan/), which works from sales rather than rooms.

Use it only in an AI product your practice has approved for its business data.

## What has been checked

Fully Powered AI wrote this capability template in its own words, drawing on one published hospital logistics method that is credited with this entry. It was editorially reviewed on 10 November 2026. It was tried on its invented example on 10 November 2026 in two runs; the record of the second, made after small fixes from its review, is published with it. It has not been tested in a medical practice, and no practice manager has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on two or three past counts your supply lead already knows, with cases written in advance: a lot that has already expired, a lot that will only partly be used, a medicine on the count, an item missing from the item list, a renamed column. The supply lead checks every par and every order line before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [Vendor quote comparison](https://fullypowered.ai/capabilities/vendor-quote-comparison/) helps when the order shows it is time to compare suppliers.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete capability template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the capability drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related capabilities

- [Inventory reorder plan](https://fullypowered.ai/capabilities/inventory-reorder-plan/)
- [Vendor quote comparison](https://fullypowered.ai/capabilities/vendor-quote-comparison/)
- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
