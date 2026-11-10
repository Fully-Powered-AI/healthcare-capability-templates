# Claim denial work list

The billing coordinator gets every denied claim from the practice’s remittance export on one work list, sorted by kind of denial, appeal deadline and amount, with the paperwork each one needs and a short summary of where denials keep starting. Staff decide every appeal.

*Capability template · Healthcare · Finance and accounting · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/claim-denial-work-list/)*

## The outcome

Denials stop sitting in a pile that gets worked in whatever order they arrived. The billing coordinator opens one list that starts with anything whose appeal deadline has already passed and anything due inside the next two weeks. Below that, every denial sits in its group, soonest deadline first and larger amounts ahead of smaller ones, with a plain statement of the records that would clear it: the clearinghouse acceptance report for a claim the payer says arrived late, the authorization on file, the patient’s insurance details for the date of service.

Denials that turn on a code or on whether a service was necessary are listed separately, for a certified coder or a clinician, with no opinion from the AI assistant. The list ends with where denials keep coming from, by payer and by provider, so the practice can fix the front-desk or referral step that causes them.

Every deadline is calculated from the practice’s own payer settings and shown with its working, so the coordinator can check it against the remittance. The aim is that no appeal window closes because nobody saw it coming.

## Who starts the work, and when

The billing coordinator starts it once a batch of remittances is posted, usually weekly, and again before month end. The billing lead or practice manager runs it to see where denials come from, and owns the payer settings and the rules it follows.

## What they supply

- The denials from the remittance export, saved as a spreadsheet file, one row per denied claim line, with patients shown as codes.
- Today’s date.
- Each payer’s appeal window and timely filing limit, in days. The capability carries none and will not guess one.
- Optionally, the practice’s own list of denial reason codes and the group each belongs to. A starter list comes with the template for the billing lead to confirm.

Nothing connects to the practice’s systems. The coordinator exports the file and supplies it. If the file’s column headings do not match what the template expects, it stops and asks rather than guessing.

## What comes out

One work list in a fixed order, opening with an outcome line and a coverage line: how many rows were read, how many are denials and for how much, how many deadlines have passed or are close, and what could not be sorted and why. Then the denials by group, each with its deadline, its working and the evidence to gather; the items for the certified coder and for the clinician; anything set aside; the patterns; and the points to check by hand.

Every section is always present, so an empty one reads “None” and a missing setting reads “Not checked”, never as a clean result. The list submits nothing, writes nothing off, contacts no one and changes no record. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the billing office of a medical practice that receives remittances with denial reason codes from several payers.
- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/): denied claims are money the practice has earned and not yet collected, and each one has a deadline.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice whose denial work lives in one coordinator’s habits and a spreadsheet nobody else reads.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding providers or payers faster than its billing office can keep track of each payer’s rules.

## What has to change for your company

Your payers come first: each one’s appeal window and filing limit, and the date each is counted from. Match the column names to your system’s export once. Confirm the starter list of reason codes against the current published code list, add the codes your payers actually use, and move any code to the group that matches who works it at your practice.

Several rules are our editorial choices, and your billing lead should confirm or change each: denials are grouped by who clears them; a passed deadline comes first and leaves its group; the order is deadline, then amount, and never by patient or provider; remark codes are shown but not interpreted; the warning window is fourteen days and a pattern is three rows. The complete list is in the template.

Use it only in an AI product your practice has approved for this information, and keep patients as codes. It does not write appeals: your staff do. For the neighbouring work, see [Receivables exception review](https://fullypowered.ai/capabilities/receivables-exception-review/) and [Prior-authorization follow-up list](https://fullypowered.ai/capabilities/prior-authorization-follow-up-list/).

## What has been checked

Fully Powered AI wrote this capability template in its own words, drawing on one published Apache-2.0 method credited in its sources. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it, and lists the small edits made afterward that have not been run again. It has not been tested in a medical practice, and no practice’s billing lead has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on a past month of denials your coordinator already knows, with cases written in advance: a deadline that has passed, a payer with no settings, a reason code missing from the map, a timely-filing denial where the claim did go out in time. The coordinator checks every deadline against the remittance before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up.

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

- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)
- [Receivables exception review](https://fullypowered.ai/capabilities/receivables-exception-review/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
