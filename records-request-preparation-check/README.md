# Records request preparation check

When a request for copies of records arrives, the records officer gets a checklist: what the request asks for, what the supplied authorization documents say, who the copies would go to, each set against the practice's own release procedure, with every gap listed. A person decides what, if anything, is released.

*Workflow template · Healthcare · Operations and process improvement · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/records-request-preparation-check/)*

## The outcome

The records officer opens a request knowing, in one page, what has been asked for, what the paperwork behind it actually says, and what is still missing. Where the request and a document disagree, both wordings sit side by side. Where the practice's own procedure asks for something the request does not carry, the gap is named, with the person who resolves it.

The response date appears exactly as counsel or privacy staff confirmed it. If no one has confirmed one, the page says so and asks. Nothing on the page is a decision to release, to refuse or to wait. Verifying who the requester is, and whether that person holds authority, stays with the records officer. What may be disclosed stays with privacy staff or counsel.

## Who starts the work, and when

The records officer, or the health information clerk who opens the practice's records requests, starts it when a request for copies arrives and again when new paperwork comes in. The practice manager owns the release procedure the check follows.

## What they supply

- The request, entered as one row: who is asking, in what role, for which patient, which records, which dates, to be sent to whom and how.
- The documents that came with it, one row each: who signed, in what role, when, what the document names, whether it is signed, how many pages arrived and how many it says it has.
- The practice's release procedure, written as numbered checks the practice already applies.
- The practice's authority records for that patient: people it already holds on file, and in what role.
- The response date, confirmed by counsel or privacy staff, with who confirmed it and when.
- Today's date.

Nothing connects to the practice's records system, and the records themselves are never supplied. No one is asked for a password or a login code.

## What comes out

One checklist in a fixed order: the request as stated, the response date as supplied, the request set against each document, each check in the practice's procedure, the gaps and open questions numbered with an owner for each, anything to look at twice, and anything that could not be assessed. Every section is always present, so an empty list reads as checked and never as forgotten.

The checklist sends nothing, releases nothing and changes no record. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): a medical practice that takes requests for copies of patient records and wants each one prepared the same way.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a release routine that lives in one person's habits becomes a procedure anyone covering the desk can follow.
- [Compliance, risk and privacy](https://fullypowered.ai/functions/compliance-risk-and-privacy/): the practice can show what was checked, what was missing and who was asked, for every request.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice with a long-serving records officer and a release routine that works until they are away.

## What has to change for your company

The release procedure is yours. The template carries no list of what an authorization must contain, no view of who may ask for what, and no response period. Write your procedure as numbered checks, each tied to a field the template reads, and name who owns each one. Keep your authority records current, because the template trusts them and nothing else. Match the column names to your own request log.

Several rules are our editorial choices for the records officer to confirm or change: names are compared after ignoring letter case and spacing, and nothing closer; a difference in wording is shown, never reconciled; a blank cell is a gap; a familiar name or email address on a request counts for nothing unless the authority records hold it; and one request is checked per run. The complete list is in the template.

Use it only in an AI product your practice has approved for patient information.

## What has been checked

Fully Powered AI wrote this workflow template from its own map of the work. It was editorially reviewed on 10 November 2026. The checklist shown in the example was worked through by hand from the template's rules. It was tried once on its invented example in Claude on 10 November 2026; that run found one cell of the example that broke the template's own rule about unreadable dates, and left several rules open. The cell and the instructions were changed afterwards and have not been run again; the record is published with the example. It has not been tested in a medical practice, and no privacy officer or counsel has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on requests your records officer has already worked, with the cases written in advance: a request wider than its authorization, an authorization with a page missing, a signer who is known to the practice only as an emergency contact, a request with no confirmed response date. The records officer compares every line with their own file. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up. [Provider credentialing tracker](https://fullypowered.ai/workflows/provider-credentialing-tracker/) is a separate routine for a clinician's licences and enrolments; this one handles a single request for copies.

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

- [Provider credentialing and re-credentialing tracker](../provider-credentialing-tracker/)
- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflow templates/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
