# Patient statement and explanation of benefits comparison

A billing specialist answering a patient’s question gets the statement and the insurer’s explanation of benefits compared line by line by service date, every unmatched amount traced to its page, and a plain-language reply drafted for approval. Nothing on the account changes.

*Workflow template · Healthcare · Finance and accounting · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/patient-statement-and-eob-comparison/)*

## The outcome

A patient calls or writes: the statement says one thing and the insurer’s explanation of benefits says another. Instead of laying two documents side by side and hunting, the billing specialist opens one comparison. Each service date is a block showing the billed, allowed, paid, adjusted and patient-responsibility amounts from both sides, whether they agree, and the page each figure came from.

Where the two differ, the comparison says what the supplied records explain, such as an insurance payment posted after the statement date, and what they do not. Amounts that appear on only one side, EOB lines that look like two versions of the same service, and pages that were never supplied are listed apart, so a real discrepancy is never mixed up with a missing page.

The comparison ends with a draft reply in plain words, one short paragraph for each line, that the billing specialist edits and approves. The specialist decides what the patient is told and whether anything on the account is adjusted.

## Who starts the work, and when

The billing specialist starts it when a patient asks why a statement differs from an explanation of benefits, usually by phone, portal message or letter. The billing lead or practice manager owns the rules it follows, such as how a match is made, and reads the patterns if the same question keeps coming back.

## What they supply

- The statement lines the patient holds, saved as a spreadsheet file, and the date printed on the statement.
- The lines of the explanation of benefits, typed or exported into a spreadsheet file with the page each line came from, and the number of pages the document says it has.
- Optionally, the account’s transaction history as a spreadsheet file, which lets the comparison account for payments posted after the statement date.
- The patient’s question, in the specialist’s words.

Patients appear as codes, never names. Nothing connects to the practice’s systems. If a file’s column headings do not match what the template expects, it stops and asks rather than guessing.

## What comes out

One comparison in a fixed order: a summary, the line-by-line blocks, the amounts that match nothing, the lines held because the explanation of benefits may have two versions, the explanation-of-benefits lines whose own arithmetic does not add up, the pages that were not supplied, and a list of things to check. Every section is always present, so an empty one reads “None”, never as a clean result.

Then the draft reply. The comparison changes no code, judges no coding or medical necessity, adjusts no account, and sends nothing.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the billing office of a medical practice that fields patient questions about statements and insurers’ explanations of benefits.
- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/): a patient’s balance is money the practice is owed, and a statement the patient cannot reconcile slows its collection.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice whose answer to this question lives in one specialist’s habits and a pair of printouts.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding providers or payers faster than its billing office can answer each statement question by hand.

For denied claims, use [Claim denial work list](https://fullypowered.ai/workflows/claim-denial-work-list/); this workflow template starts from a patient’s question about two documents, not from a denial. For the neighbouring work, see [Receivables exception review](https://fullypowered.ai/workflows/receivables-exception-review/).

## What has to change for your company

Match the column names to your system’s export once. Decide how your practice treats a statement that was printed before a payment posted, and who tells the patient. Confirm the rules that are our editorial choices: a match needs the same service date and the same billed amount; two explanation-of-benefits lines for one service are held rather than picked between; amounts must agree to the cent; and the draft reply states recorded facts and promises nothing.

Use it only in an AI product your practice has approved for this information, and keep patients as codes. It does not write to the patient or the insurer: your staff do, and your staff decide any adjustment. Questions about codes or whether a service was necessary go to your certified coder or the treating clinician.

## What has been checked

Fully Powered AI wrote this workflow template in its own words, from its own published map of the work. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it, and lists the small edits made afterward that have not been run again. It has not been tested in a medical practice, and no practice’s billing lead has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on past patient questions your specialist has already answered, with cases written in advance: a payment posted after the statement date, a patient payment missing from the balance, a service on one document and not the other, a page not supplied. The specialist checks every figure against both documents before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Claim denial work list](../claim-denial-work-list/)
- [Receivables exception review](https://fullypowered.ai/workflow templates/receivables-exception-review/)
- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
