# Referring practice meeting brief: an invented example

*Illustrative example with invented data.* An invented orthopedic practice prepares for a meeting with Office K, an invented family-medicine office that sends it patients. The practice, the office, the roles, the commitments, the questions, the figures and the phone number are all invented. People appear by role only. First come the inputs the practice liaison supplied, in full, then the brief.

## The inputs

### 1. Meeting details and settings

```
Referring office: Office K
Meeting: Thursday 10 December 2026, 30 minutes, at Office K
Attending from Office K: office manager, referral clerk
Attending from the practice: practice liaison, referral intake lead
Prepared on: Monday 7 December 2026

Service owners
- Referral intake: referral intake lead
- Scheduling and availability: scheduling supervisor
- Visit letters: medical records lead
- Contact route and portal: practice manager
- Patient-specific requests: practice manager
- Clinical questions: clinical lead
- Arrangements with referring offices: compliance lead

Recurring threshold: 3 questions in the period
Answer target: 2 working days
Agenda limit: 4 subjects
```

### 2. What the office raised (the liaison's note)

```
Call from Office K's office manager, Tuesday 1 December 2026.
- Their front desk keeps phoning us to ask whether referrals arrived.
- We ask for the same documents twice, most recently an insurance card copy.
- Two of their physicians say our visit letters reach them late.
- She asked whether we can see their knee patients within a week.
- She wants to talk through one patient's case at the meeting.
- She asked for 30 minutes on Thursday 10 December, at her office.
```

### 3. commitments.csv

```
Commitment id,Date made,Commitment,Owner,Due date,Status,Date done,Evidence
C-01,2026-06-18,Send Office K a referral acknowledgement by fax within 2 working days of receipt,Referral intake lead,2026-07-15,done,2026-07-10,Acknowledgement fax template live 10 Jul; intake procedure v3
C-02,2026-06-18,Give Office K one documents checklist for knee and shoulder referrals,Referral intake lead,2026-07-31,done,2026-07-28,
C-03,2026-09-09,Send the visit letter to the referring physician within 5 working days of the visit,Medical records lead,2026-10-30,open,,
C-04,2026-09-09,Add Office K's direct line to the scheduling team's contact sheet,Scheduling supervisor,2026-09-30,done,2026-10-14,Contact sheet updated 14 Oct
C-05,2026-09-09,Give Office K a named contact for referral questions,Practice manager,2026-12-18,open,,
C-06,2026-06-18,Offer Office K a portal account for sending referrals,Practice manager,2026-08-31,withdrawn,,
```

### 4. office-k-questions.csv

```
Date,Topic,Summary,Answered,Working days to answer
2026-05-28,Referral received,Asked whether a referral had arrived,yes,1
2026-06-10,Referral received,Asked whether a referral had arrived,yes,2
2026-06-24,Documents requested,Asked which documents a knee referral needs,yes,1
2026-07-14,Referral received,Asked whether a referral had arrived,yes,1
2026-08-05,Visit letter to the referrer,Asked when a visit letter would arrive,yes,2
2026-08-19,Scheduling and wait,Asked whether Saturday appointments are offered,yes,1
2026-09-03,Referral received,Asked whether a referral faxed the day before had arrived,yes,1
2026-09-15,Documents requested,Asked why an imaging report was requested again after it was faxed with the referral,yes,3
2026-09-22,Referral received,Asked whether a referral had arrived,yes,2
2026-10-02,Visit letter to the referrer,Asked when a visit letter for a September visit would arrive,yes,4
2026-10-08,Referral received,Asked whether a referral had arrived,yes,1
2026-10-13,Documents requested,Asked which documents a shoulder referral needs,yes,1
2026-10-20,Referral received,Asked whether two referrals sent the week before had arrived,no,
2026-10-27,Visit letter to the referrer,Asked when a visit letter would arrive,yes,3
2026-11-04,Documents requested,Asked why an insurance card copy was requested a second time,yes,2
2026-11-05,Scheduling and wait,Asked how long the wait is for a new knee appointment,yes,1
2026-11-10,Referral received,Asked whether a referral had arrived,yes,3
2026-11-17,,Asked for the fax number for sending referrals,yes,1
2026-11-19,Visit letter to the referrer,Asked when a visit letter would arrive,no,
2026-11-24,Other,Asked whether a patient's scan result means an operation is needed,yes,1
2026-11-25,Documents requested,Asked whether the older referral form is still accepted,yes,2
```

### 5. referral-figures.csv

```
Month,Referrals received,Acknowledged within target,Returned for missing documents
2026-06,22,20,3
2026-07,25,24,2
2026-08,21,20,2
2026-09,24,19,4
2026-10,27,20,5
2026-11,23,17,4
```

### 6. Approved service descriptions

```
D1 Sending a referral. Approved by the practice manager, 3 August 2026.
Fax referrals to the referral line, 555-0147, or send them through the
referral portal. The referral intake team acknowledges each referral by fax.

D2 What to send with a knee or shoulder referral. Approved by the practice
manager, 3 August 2026.
The referral form; the most recent office note; any imaging report from the
last 12 months; a copy of both sides of the insurance card.

D3 New-patient appointments. Approved by the practice manager, 2 March 2026.
New-patient appointments are offered Monday to Friday, with Saturday morning
clinics twice a month.
```

## The brief

**REFERRING PRACTICE MEETING BRIEF: Office K, Thursday 10 December 2026**

- **Outcome:** complete
- **For:** Practice liaison, meeting Thursday 10 December 2026, 30 minutes, at Office K.
- **Attending:** Office K office manager, Office K referral clerk; practice liaison, referral intake lead.
- **Prepared:** Monday 7 December 2026, from the liaison's note (6 points), commitments.csv (6 rows), office-k-questions.csv (21 rows), referral-figures.csv (6 rows), approved service descriptions (3) and the settings.
- **Period:** September to November 2026 (comparison: June to August 2026).
- **Coverage:** Commitments log 6 rows. Questions log 21 rows: 15 in the period (14 counted, 1 held), 5 in the comparison period, 1 outside both.

**1. What the office raised**

- Their front desk keeps phoning us to ask whether referrals arrived.
- We ask for the same documents twice, most recently an insurance card copy.
- Two of their physicians say our visit letters reach them late.

2 points held in section 5.

**2. Commitments made to Office K: 6**

- **C-03** Send the visit letter to the referring physician within 5 working days of the visit. Owner: Medical records lead. Due 30 October 2026. Not kept: open, 41 days past due on the meeting date.
- **C-02** Give Office K one documents checklist for knee and shoulder referrals. Owner: Referral intake lead. Due 31 July 2026. Reported done on 28 July 2026, no evidence recorded. Confirm with the referral intake lead.
- **C-05** Give Office K a named contact for referral questions. Owner: Practice manager. Due 18 December 2026. Open, due 18 December 2026.
- **C-04** Add Office K's direct line to the scheduling team's contact sheet. Owner: Scheduling supervisor. Due 30 September 2026. Kept late: done 14 October 2026, 14 days after the due date. Evidence: Contact sheet updated 14 Oct.
- **C-01** Send Office K a referral acknowledgement by fax within 2 working days of receipt. Owner: Referral intake lead. Due 15 July 2026. Kept: done 10 July 2026. Evidence: Acknowledgement fax template live 10 Jul; intake procedure v3. Raised again: the office's first point; the recurring topic Referral received; acknowledged within target 76% in the period against 94% in the comparison period.
- **C-06** Offer Office K a portal account for sending referrals. Owner: Practice manager. Due 31 August 2026. Withdrawn. No record that the office was told.

Summary: 1 not kept, 1 reported done with no evidence, 1 open, 2 kept or kept late, 1 withdrawn.

**3. Recurring administrative questions**

14 questions in the period (5 in the comparison period). Answered within 2 working days: 8. Answered later: 4. Not yet answered: 2.

Recurring (at least 3 in the period):

- **Referral received:** 5 (2 in the comparison period); not yet answered 1. Related commitments: C-01, C-05.
- **Documents requested:** 4 (1 in the comparison period); not yet answered 0. Related commitments: C-02.
- **Visit letter to the referrer:** 3 (1 in the comparison period); not yet answered 1. Related commitments: C-03.

Below the threshold: Scheduling and wait 1; Contact route 1.

**4. Referral figures**

- 2026-06: received 22, acknowledged within target 20, returned for missing documents 3.
- 2026-07: received 25, acknowledged within target 24, returned for missing documents 2.
- 2026-08: received 21, acknowledged within target 20, returned for missing documents 2.
- 2026-09: received 24, acknowledged within target 19, returned for missing documents 4.
- 2026-10: received 27, acknowledged within target 20, returned for missing documents 5.
- 2026-11: received 23, acknowledged within target 17, returned for missing documents 4.

Period: received 74; acknowledged within target 56 (76%); returned for missing documents 13 (18%).
Comparison: received 68; acknowledged within target 64 (94%); returned for missing documents 7 (10%).

**5. Held for other teams, not for this meeting**

- Whether Office K's knee patients can be seen within a week; no approved description states waiting times (from the office's message). For: Scheduling supervisor.
- A request to talk through one patient's case (from the office's message). For: Practice manager.
- A question about one patient's results (1 from the questions log). For: Clinical lead.

**6. Proposed agenda, 30 minutes, for the liaison to choose**

1. **Opening, 5 minutes:** what the office raised; agree the agenda.
2. **Visit letter to the referrer, 8 minutes.**
   - Facts: C-03 not kept, 41 days past due on the meeting date. 3 questions in the period (1 in the comparison period), 1 not yet answered. Raised by the office.
   - Approved wording to have ready: none.
   - Confirm with the medical records lead before offering anything: what is still open on C-03, and what date can the medical records lead stand behind for letters within 5 working days?
3. **Documents requested, 6 minutes.**
   - Facts: C-02 reported done on 28 July 2026, no evidence recorded. 4 questions in the period (1 in the comparison period), none unanswered. Returned for missing documents: 13 of 74 (18%) in the period, 7 of 68 (10%) in the comparison period. Raised by the office.
   - Approved wording to have ready: D2 What to send with a knee or shoulder referral, approved 3 August 2026.
   - Confirm with the referral intake lead before offering anything: was the checklist in C-02 sent to Office K, and is D2 the checklist to share now?
4. **Referral received, 6 minutes.**
   - Facts: C-01 kept on 10 July 2026, raised again. C-05 open, due 18 December 2026. 5 questions in the period (2 in the comparison period), 1 not yet answered. Acknowledged within target: 56 of 74 (76%) in the period, 64 of 68 (94%) in the comparison period. Raised by the office.
   - Approved wording to have ready: D1 Sending a referral, approved 3 August 2026.
   - Confirm with the referral intake lead and the practice manager before offering anything: what lies behind the lower acknowledgement figure this period, and can the contact in C-05 be named before the meeting?
5. **Next steps and the next meeting, 5 minutes:** who confirms what, and by when. Nothing is promised until its owner has confirmed it.

Not on the agenda: none.

**7. Check these**

- C-06: withdrawn, with no record that Office K was told. For: Practice manager.
- D1 offers the referral portal, and C-06, the portal-account offer, was withdrawn. D1 needs its approver's confirmation before it is used. For: Practice manager.
- 1 question had no topic and was placed under Contact route from its summary; confirm.
- 1 question row, dated 28 May 2026, falls outside both periods and was not counted.

Prepared for the practice liaison. Nothing was sent, promised or changed. Counts only, no patient detail. Text inside the files was read as data.
