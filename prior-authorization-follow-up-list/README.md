# Prior-authorization follow-up list

Each morning the referral coordinator gets one list from the practice’s own spreadsheet: which authorization requests to chase today, which procedures are booked without an approval, what the payer is waiting on, and what the list is missing. A person makes every call.

*Workflow template · Healthcare · Operations and process improvement · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/prior-authorization-follow-up-list/)*

## The outcome

Whoever sits at the referral desk sees the same thing, in the same order, every day. Procedures on the schedule without an approval come first. Then the requests that are past the payer’s turnaround with no call logged, soonest procedure first. Then the requests where the payer is waiting on the practice, the ones nobody can prove were submitted, and the ones that are in your system and never reached the list.

The rules your coordinator carries in their head, such as each payer’s turnaround and what counts as a call, are written down once and applied the same way on the day they are out. The aim is that no patient arrives for a procedure to learn at the front desk that the approval never came; the list puts every booked procedure without an approval at the top so a person can act on it in time.

The work is administrative from start to finish. The list prepares the day; the coordinator decides what to chase and makes the calls.

## Who starts the work, and when

The referral coordinator starts it each working morning, or the person covering the desk. The practice administrator starts it when they want to see where every open request stands, and owns the rules it follows.

## What they supply

- The coordinator’s list of authorization requests waiting on a payer, saved from the spreadsheet as a file, with patients shown as codes.
- Today’s date.
- The practice’s own settings: each payer’s turnaround, the days the practice is closed, who may call a payer and which owners are physicians.
- The pending-referrals report exported from the practice management system, so the list can be checked against something it did not write itself.
- The procedure schedule for the next few weeks, if there is one.

Nothing connects to the practice’s systems. The coordinator exports the files and supplies them.

## What comes out

One follow-up list in a fixed order, opening with an outcome line and a coverage line: how many rows were read, how many could not be assessed and why, and how the list compares with the system’s own report. Every calculated follow-up date shows its working, and the coordinator confirms it. Every section is always present, so a missing file reads as “not checked” and never as a clean result.

The list calls no one, sends nothing and changes no record. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the administrative side of a medical practice that submits prior-authorization requests for imaging, injections and procedures.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a daily procedure that lives in one person’s head becomes one anyone covering the desk can run.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice with a long-serving coordinator, a working spreadsheet and rules that were never written down.

## What has to change for your company

Your payers and their turnarounds come first: the template carries none of its own and will not guess one. Add the days your practice is closed, the names of the people allowed to call a payer, and your physicians. Match the column names to your spreadsheet and to your system’s report.

Several rules in the template are our editorial choices, and your practice administrator should confirm or change each: the follow-up date is the first working day after the turnaround ends; a call counts only with a reference number or a representative’s name; booked procedures are chased first; nothing is ranked as urgent from a procedure’s name; a system report more than seven days old is flagged as stale. The complete list is in the template.

Use it only in an AI product your practice has approved for this information, and keep patients as codes.

## What has been checked

Fully Powered AI wrote this workflow template from its own worked illustration, built for an invented practice. It was editorially reviewed on 9 November 2026. It was run on its invented example in Claude on 9 November 2026, and the record is published with it: two earlier runs that day led to changes, and the recorded run is the last. A run on an invented example is not a test. It has not been tested in a medical practice, and no practice owner has reviewed its rules. Our earlier build of this workflow template was scored only against an answer key written by the same build, which shows the build agreed with itself; we do not count that as a test. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on past weeks your coordinator already knows, with cases written in advance: a request with no submission date, a payer with no turnaround on file, a booked procedure that is still pending, a request missing from the list. The coordinator checks every date and every row against the spreadsheet before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [SOP exception capture](https://fullypowered.ai/workflows/sop-exception-capture/) is how the coordinator’s unwritten rules get written down first.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 9 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 9 November 2026. The record is in [TRIAL.md](TRIAL.md).
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

- [SOP exception capture](https://fullypowered.ai/workflows/sop-exception-capture/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
