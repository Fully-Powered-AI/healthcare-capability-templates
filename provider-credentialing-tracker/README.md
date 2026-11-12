# Provider credentialing and re-credentialing tracker

The credentialing coordinator keeps one tracker per clinician: each licence, registration, certification, insurance policy and payer enrolment, where it was verified, when it falls due, the day its renewal should start, and which files are not yet complete. A person contacts every board and payer.

*Workflow template · Healthcare · Operations and process improvement · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/provider-credentialing-tracker/)*

## The outcome

Nothing lapses because the date lived in someone's inbox. Every clinician has one page listing each item your practice requires, where it was confirmed, the date it runs out or next needs checking, and the date work on it should begin, counted back from that deadline by the lead time you set.

Above the pages sit the lists the coordinator works from: anything already lapsed, what to start now, what starts in the next few weeks, what is waiting on a board, insurer or payer, and every file that is not yet complete, with each reason spelled out. A new clinician's file comes first, with the days left before their first day.

The work is administrative from start to finish. The tracker follows documents and dates. Privileges, peer review and any view of a clinician's competence stay with your medical director and medical leadership, and the tracker says so on every run.

## Who starts the work, and when

The credentialing coordinator starts it each week or at the start of each month, and whenever a clinician is about to join. In a smaller practice the practice manager runs it. The practice manager owns the list of required items and the lead times it follows.

## What they supply

- The clinician roster, saved from your records as a file: each clinician's type, whether they are active or joining, and a joining clinician's start date.
- The coordinator's spreadsheet of credential items, saved as a file: for each item, who issued it, where and when it was verified and by whom, its expiry, whether the document is on file, and whether a renewal or application is in.
- Your requirements: which items each type of clinician needs, how each one falls due, how many days ahead work should start, and which verification source you accept.
- Today's date.

Nothing connects to your systems or to any board's or payer's website, and no one is asked for a login. The coordinator looks each item up and records it, then supplies the files.

## What comes out

One tracker in a fixed order, opening with an outcome line and a coverage line: how many clinicians and rows were read, which required items have no row at all, and anything that could not be read. Then the lists to act on, each item with its due date and start date shown, then a page for every clinician. Every section is always present, so an empty list reads as checked and never as forgotten.

The tracker contacts no one, submits nothing and changes no record. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the administrative side of a medical practice that keeps its clinicians' licences, insurance and payer enrolments current.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a calendar of deadlines that lives in one person's head becomes a routine anyone covering the desk can run.
- [Compliance, risk and privacy](https://fullypowered.ai/functions/compliance-risk-and-privacy/): the practice can see at any moment which files are complete and which are not, and why.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice with a long-serving coordinator and a spreadsheet that works until they are away.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding clinicians, where every new file has to be ready before the first day.

## What has to change for your company

Your requirements come first: the template carries none of its own and will not guess one. List your clinician types and the items each needs, say how each item falls due and how far ahead work should start, and name the verification source you accept for each. Confirm those rules with the bodies concerned; the template does not judge what any regulation or payer asks for. Match the column names to your roster and your spreadsheet.

Several rules are our editorial choices for your practice manager to confirm or change: an item is valid through its due date; a renewal applied for does not stop an item counting as lapsed; a copy supplied by the clinician does not count as verified unless you say it does; and an item marked "not started" counts as missing. The complete list is in the template.

Use it only in an AI product your practice has approved for staff records.

## What has been checked

Fully Powered AI wrote this workflow template, drawing on a published hospital credentialing method by CaseMark under the Apache-2.0 licence and scaling it down to a medical practice. It was editorially reviewed on 10 November 2026. The tracker shown in the example was worked through by hand from the template's rules. The template was then tried once on its invented example in Claude on 10 November 2026, and the record is published with it: the output agreed with the example on every standing, date and count, the model brought its wording into line with the example's before the record was saved, and the stop and decline paths were not exercised. Small edits made afterward, listed in the record, have not been run again. It has not been tested in a medical practice, and no credentialing professional has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on a month your coordinator already knows, with cases written in advance: an item that lapsed last week, a renewal applied for after the deadline passed, a required item with no row, a joining clinician with an application still open. The coordinator checks every date against the spreadsheet before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [Prior-authorization follow-up list](https://fullypowered.ai/workflows/prior-authorization-follow-up-list/) is the companion routine for the referral desk.

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

- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflow templates/pilot-acceptance-test-preparation/)
- [SOP exception capture](https://fullypowered.ai/workflow templates/sop-exception-capture/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
