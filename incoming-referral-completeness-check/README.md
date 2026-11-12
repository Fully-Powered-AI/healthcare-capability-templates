# Incoming referral completeness check

When a referral arrives, the coordinator gets one checklist: what the referring office sent, held against the practice's own referral checklist, what is missing or needs a new copy, and a draft request for exactly those items. A clinician sets urgency; nothing is sent until the coordinator approves it.

*Workflow template · Healthcare · Operations and process improvement · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/incoming-referral-completeness-check/)*

## The outcome

Every referral gets the same check on the day it lands, against the list your practice already keeps. The coordinator sees in one place what arrived, what is missing, and what came but will not do: an order nobody signed, a visit note older than your limit, an insurance card copied on one side. Each gap is already written into a request to the referring office, so that office is asked once, for everything, instead of piece by piece as each gap turns up at booking.

The check is administrative from start to finish. It reports the urgency the referrer marked exactly as written and copies any note about the patient's health word for word for your reviewing clinician, so a worried phone call is never held up behind a missing insurance card. It never decides how soon anyone is seen, whether a referral is appropriate or whether the clinical information is enough. Your coordinator confirms the referral is ready; your clinician sets urgency and clinical requirements.

## Who starts the work, and when

The referral coordinator or scheduling coordinator starts it when a referral and its attachments reach the desk, before anyone books, and again each time the referring office sends more. Whoever is covering the desk can run it the same way. The practice administrator owns the referral checklist it applies.

## What they supply

- The date the referral was received.
- Your practice's own referral checklist, saved as a spreadsheet file: each item, the services it applies to, whether it is always needed or only in a stated case, where it is found, how recent a document must be, and whether it must be signed.
- The referral form's fields, copied or typed, with the patient shown as a code.
- A short list of the attachments received, which the coordinator fills in on receipt: each document's type and date, whether it is signed, complete and readable, and whether its patient details match the form.
- Any intake notes, such as a phone call about the referral.
- Your settings: the services you accept, the roles involved, your request wording and how the referring office should send documents back.

Nothing connects to your systems, and the template carries no checklist of its own. If a spreadsheet's column headings do not match what the template expects, it stops and asks rather than guessing.

## What comes out

One check in a fixed order. A header gives the referral, where it is going, an outcome and the counts. Then the checklist item by item, the points for the coordinator to look at, documents received that the checklist does not ask for, the destination, a section for the reviewing clinician, and the draft request to the referring office. Every section is always present, so an empty one reads "None" rather than disappearing.

A document whose patient details do not match is set aside and never forwarded or mentioned in the request. When the referral names a service your practice does not list, the request is held until the practice administrator decides. The check sends nothing, books nothing and changes no record, and it ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the referral desk of a specialist or outpatient practice that receives referrals from other offices.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a referral checklist that lives in one coordinator's habits becomes one anyone covering the desk applies the same way.
- [Customer support and service](https://fullypowered.ai/functions/customer-support-and-service/): the patient-access desk, where a complete referral is the difference between a booked visit and a callback.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice with a long-serving coordinator and a checklist that was never fully written down.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding services or referring offices faster than the desk can keep every requirement in its head.

## What has to change for your company

Your referral checklist comes first: the items, which services each one applies to, how recent each document must be and which ones need a signature. Your practice administrator writes it, with your clinicians agreeing anything clinical on it. Then match the field names to your referral form, set the urgency wording your referrers use for routine, and write the opening and closing your practice uses when it asks a referring office for more.

Several rules are our editorial choices, and your practice administrator should confirm or change each: document age is counted in calendar days from the day the referral arrived; a document with mismatched patient details is set aside; the request waits while the destination is unclear; clinical fields are reported only as filled or blank; a blank urgency mark goes to the clinician at once. The complete list is in the template.

Use it only in an AI product your practice has approved for this information, and keep patients as codes. For the payer side of the same referral, see [Prior-authorization follow-up list](https://fullypowered.ai/workflows/prior-authorization-follow-up-list/); for the bookings that follow, see [Appointment confirmation and no-show follow-up](https://fullypowered.ai/workflows/appointment-confirmation-and-no-show-follow-up/).

## What has been checked

Fully Powered AI wrote this workflow template from its own published map of healthcare work. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it, with the edits made after the first run and review, and the template was run again on the example after the last of them. It has not been tested in a medical practice, and no practice administrator has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on past referrals your coordinator already knows, with cases written in advance: an unsigned order, a visit note past your limit, a document belonging to another patient, a referral to a service you do not offer, a phone call about the patient's health. The coordinator opens every document and checks every line before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up.

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
- [Appointment confirmation and no-show follow-up](../appointment-confirmation-and-no-show-follow-up/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
