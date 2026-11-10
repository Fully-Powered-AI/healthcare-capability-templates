# Dental lab case tracker

The office coordinator keeps one tracker of every case at an outside dental lab: when it went, the lab's due date against the patient's seating, which cases are overdue or due back too late, each remake with its stated reason, and each lab's on-time record for the quarter. A person calls every lab.

*Capability template · Healthcare · Operations and process improvement · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/dental-lab-case-tracker/)*

## The outcome

No patient sits in the chair for work that is still at the lab. Every case out at a lab is set against the patient's seating appointment, with a few days held back so the dentist can look the work over first, and the coordinator sees each morning which cases to chase, which seatings are already in danger, and which patients still need booking.

Once a quarter the office has each lab's record from its own dates: how many cases came back on time, how many late and by how many days, how long cases took on average, what is still out past its date, and which cases had to be remade, with the reason the office recorded. The conversation with a lab starts from facts rather than impressions.

The work is administrative from start to finish. The dentist writes every prescription, chooses shade and material, judges whether the work fits and decides on any remake. The tracker never reads, fills in or comments on any of that, and says so on every run.

## Who starts the work, and when

The office coordinator runs it each morning or at the start of each week, and the office manager runs it at the end of each quarter or before a meeting with a lab. In a smaller office the front-desk lead runs it. The office manager owns the settings it follows.

## What they supply

- The lab case list, saved from the office's spreadsheet or practice software as a file: for each case, the patient reference, the dentist, the lab, the office's own label for the work, the date sent, the lab's due date, the seating appointment, the date received, its status, and, for a remake, the earlier case and the reason the office recorded.
- The office's settings: how many days before the seating a case must be back, how far ahead counts as "due back soon", and the quarter to report.
- Today's date.

Nothing connects to your practice software or to any lab's portal, and no one is asked for a login. Columns such as shade or material can stay in the export: the tracker leaves them unread and never repeats them.

## What comes out

One tracker in a fixed order, opening with an outcome line and a coverage line: how many cases were read, how many are at the lab, back or cancelled, and anything that could not be read. Then the lists to act on: overdue from the lab, due back too late for the seating, at the lab with no seating booked, due back in the next few days, on track, and back and waiting for the seating. Then every remake sent this quarter with its reason copied as written, and a short record for each lab. Every section is always present, so an empty list reads as checked and never as forgotten.

The tracker contacts no one, books nothing and changes no record. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the front office of a dental practice that sends crowns, bridges, dentures and guards to outside labs.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a set of dates spread across a spreadsheet and a lab's emails becomes one routine anyone covering the desk can run.
- [Procurement and suppliers](https://fullypowered.ai/functions/procurement-and-suppliers/): each lab is a supplier, and the quarter's record shows how it keeps its dates.
- [Quality management](https://fullypowered.ai/functions/quality-management/): every remake is logged with the reason the office recorded, so the pattern is visible without anyone guessing at a cause.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): an office with a long-serving coordinator who knows every case by heart until they are away.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): an office adding dentists or chairs, where the number of cases out at once outgrows memory.

## What has to change for your company

Match the column names to your own export, and decide what the patient reference is; a chart number keeps names out of the tracker. Set the check-in days to the time your dentists want a case in the office before the patient arrives, and the look-ahead to how far ahead your coordinator plans.

Several rules are our editorial choices for your office manager to confirm or change: days are counted in calendar days; a case received on the lab's date is on time; an overdue case is listed first whatever its seating; a case with no seating booked is listed on its own; and a remake counts toward the lab that made the earlier case, with no view on whose fault it was. The record sets no targets and ranks no lab. The complete list is in the template.

Use it only in an AI product your office has approved for patient-related records.

## What has been checked

Fully Powered AI wrote this capability template, drawing on a published dental laboratory coordination method by CaseMark under the Apache-2.0 licence and keeping only its case-tracking and lab-record ideas. It was editorially reviewed on 10 November 2026. The tracker shown in the example was worked through by hand from the template's rules. The template, with the small edits made on review, was then tried on its invented example in Claude on 10 November 2026, and the record is published with it: every case, date and count agreed with the example's tracker, and four lines differed in wording. That run did not reach the lines for a case not yet overdue whose seating has already passed, or for an overdue case with too few days left before the seating, and the stop and decline paths were not exercised. It has not been tested in a dental office, and no dental professional has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your office means running it on a few weeks your coordinator already knows, with cases written in advance: a case overdue with the seating two days away, a case due back on the seating day, a remake with no reason recorded, a case received before the quarter began. The coordinator checks every date against the case list before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [Supplier issue notice](https://fullypowered.ai/capabilities/supplier-issue-notice/) prepares the formal note to a lab when its record calls for one.

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

- [Provider credentialing and re-credentialing tracker](../provider-credentialing-tracker/)
- [Supplier issue notice](https://fullypowered.ai/capabilities/supplier-issue-notice/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
