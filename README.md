# Fully Powered Capability Templates: Healthcare

A practice where no patient waits on paperwork nobody chased. These capability templates are written for the people who run the administrative side of a medical practice. They prepare administrative work only. They give no clinical advice, and the practice's staff make every decision and every call.

This repository holds 10 capability templates for practice administrators and coordinators. Each one is a single piece of work with its own folder: what it is for and who starts it, the complete template an AI assistant follows, a worked example with invented data, what to change for your company, what has been checked, and its sources.

## The capabilities

- **[Appointment confirmation and no-show follow-up](appointment-confirmation-and-no-show-follow-up/)**: The front desk gets tomorrow’s bookings from the appointment export with the practice’s approved script or message filled in for each, every reply recorded once staff have called, and today’s no-shows with open slots to offer them. Staff make every call and every diary change.
- **[Claim denial work list](claim-denial-work-list/)**: The billing coordinator gets every denied claim from the practice’s remittance export on one work list, sorted by kind of denial, appeal deadline and amount, with the paperwork each one needs and a short summary of where denials keep starting. Staff decide every appeal.
- **[Clinic supply par levels and expiry check](clinic-supply-par-levels-and-expiry-check/)**: From the clinic's own stock-count and usage exports, the person who orders supplies gets a par level and reorder point for every item in every room, what is below par, what will expire before it is used, and a draft order. Medical-surgical and office supplies only; a person approves every order.
- **[Dental lab case tracker](dental-lab-case-tracker/)**: The office coordinator keeps one tracker of every case at an outside dental lab: when it went, the lab's due date against the patient's seating, which cases are overdue or due back too late, each remake with its stated reason, and each lab's on-time record for the quarter. A person calls every lab.
- **[Incoming referral completeness check](incoming-referral-completeness-check/)**: When a referral arrives, the coordinator gets one checklist: what the referring office sent, held against the practice's own referral checklist, what is missing or needs a new copy, and a draft request for exactly those items. A clinician sets urgency; nothing is sent until the coordinator approves it.
- **[Patient statement and explanation of benefits comparison](patient-statement-and-eob-comparison/)**: A billing specialist answering a patient’s question gets the statement and the insurer’s explanation of benefits compared line by line by service date, every unmatched amount traced to its page, and a plain-language reply drafted for approval. Nothing on the account changes.
- **[Prior-authorization follow-up list](prior-authorization-follow-up-list/)**: Each morning the referral coordinator gets one list from the practice’s own spreadsheet: which authorization requests to chase today, which procedures are booked without an approval, what the payer is waiting on, and what the list is missing. A person makes every call.
- **[Provider credentialing and re-credentialing tracker](provider-credentialing-tracker/)**: The credentialing coordinator keeps one tracker per clinician: each licence, registration, certification, insurance policy and payer enrolment, where it was verified, when it falls due, the day its renewal should start, and which files are not yet complete. A person contacts every board and payer.
- **[Records request preparation check](records-request-preparation-check/)**: When a request for copies of records arrives, the records officer gets a checklist: what the request asks for, what the supplied authorization documents say, who the copies would go to, each set against the practice's own release procedure, with every gap listed. A person decides what, if anything, is released.
- **[Referring practice meeting brief](referring-practice-meeting-brief/)**: Before meeting a referring office that has raised handoff problems, the practice liaison gets one brief: what was promised to that office and whether each promise was kept, the questions its staff keep asking, counted by topic, and a proposed agenda. Counts only, no patient detail; the liaison decides.

## How to use one

Open a folder and start with its README. Every folder stands alone, so copy the one you want and leave the rest. The templates are written for ChatGPT, Claude, Copilot and Gemini: paste the instruction block and the output format in as custom instructions, or load the folder in a product that reads `SKILL.md` packages.

In every template a person starts the work, supplies the inputs and decides. The template prepares and checks. Anything that sends, posts, pays or changes a record waits for a person to approve it.

## What "checked" means here

Each folder says exactly what was checked and when: who wrote it, that its sources and rights were reviewed, the date of its editorial review, and whether it has been tried on its invented example in a named AI product. Nothing is described as tested for a client unless it was. Test a template on your own past work before your team relies on it; each one comes with acceptance tests for that.

## More capabilities

The [Fully Powered Capabilities Directory](https://fullypowered.ai/capabilities/) lists every capability across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the capability drew on. Published by [Fully Powered AI](https://fullypowered.ai/).
