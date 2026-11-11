# Incoming referral completeness check: an invented example

*Illustrative example with invented data.* An invented sleep medicine practice, Sleep Practice A, receives a referral from an invented family practice, Family Practice B, on Tuesday 17 November 2026. The practices, the referring doctor, the patient code, the documents and the dates are all invented. The inputs the referral coordinator supplied come first, in full, then the check.

## What the coordinator supplied

**The request**

> Referral RF-2291 came in this morning, 17 November 2026. Here are our checklist, the form, my attachment list, my intake notes and our settings. What is missing?

**The practice's settings**

```
Practice: Sleep Practice A
Services we accept: Sleep consultation; Home sleep test
Coordinator: referral coordinator
Reviewing clinician: reviewing sleep physician
Practice administrator: practice manager
Field names on the form: the defaults
Routine urgency wording: Routine
Request opening: Thank you for referring your patient to us. To complete
  the referral, please send the following.
Return route: to our referral fax line
Reply window: 5 working days
Request closing: Referral desk, Sleep Practice A
```

**The practice's checklist: referral-checklist.csv**

```
Item id,Item,Service,Required,Source,Match,Within days,Signature needed
R01,Referring clinician named,All,Always,Form,Referring clinician,,No
R02,Reason for referral completed,All,Always,Form,Reason for referral,,No
R03,Insurance plan stated,All,Always,Form,Insurance plan,,No
R04,Signed referral order,All,Always,Attachment,Referral order,90,Yes
R05,Insurance card copy (front and back),All,Always,Attachment,Insurance card,,No
R06,Most recent office visit note,All,Always,Attachment,Office visit note,180,No
R07,Current medication list,All,Always,Attachment,Medication list,90,No
R08,Prior sleep study report,Sleep consultation,If Prior sleep study = Yes,Attachment,Sleep study report,,No
R09,Sleepiness questionnaire,Home sleep test,Always,Attachment,Sleepiness questionnaire,90,No
R10,Referral authorization number,All,If Authorization required = Yes,Form,Authorization number,,No
```

**The referral form, typed from the fax, patient shown as a code**

```
Referral reference: RF-2291
Patient: PT-5108
Referring office: Family Practice B
Referring clinician: Dr. Tamsin Vell
Referred to: Sleep consultation
Urgency: Routine
Reason for referral: Loud snoring and daytime sleepiness; partner has
  noticed pauses in breathing at night.
Insurance plan: Plan C
Prior sleep study: Yes
```

**The attachment index: attachments-RF-2291.csv**

```
Attachment,Document type,Document date,Signed,Complete and legible,Identifiers match
A1,Referral order,2026-11-12,No,Yes,Yes
A2,Insurance card,2026-11-12,,No,Yes
A3,Office visit note,2026-03-02,,Yes,Yes
A4,Medication list,2026-11-12,,Yes,No
A5,Lab results,2026-10-30,,Yes,Yes
```

**The intake notes**

```
17 Nov, 08:40. Referral from Family Practice B arrived by fax, 11 pages.
17 Nov, 10:15. Patient's wife phoned to ask whether he can be seen
  before the holidays; says he nodded off at the wheel last week.
```

## What came back

*The check comes back as plain text. It is shown here with bold headings and bullets so it is easier to read on a page; the words, the order and the figures follow the template's output format.*

**INCOMING REFERRAL COMPLETENESS CHECK**

- Referral RF-2291 from Family Practice B, received Tuesday 17 November 2026.
- Referred to: Sleep consultation (on the practice's list).
- Outcome: not complete
- Counts: 9 items for this referral: 3 received, 3 to check, 2 missing, 1 applies? not stated, 0 not required, 0 not checked. 1 item for other services only.
- Inputs: checklist "referral-checklist.csv", 10 items; form, 9 fields; attachment index "attachments-RF-2291.csv", 5 attachments; intake notes supplied.

**1. The checklist**

- R01 Referring clinician named: Received (form).
- R02 Reason for referral completed: Received (form).
- R03 Insurance plan stated: Received (form).
- R04 Signed referral order: Received, check (A1): not signed.
- R05 Insurance card copy (front and back): Received, check (A2): incomplete or illegible.
- R06 Most recent office visit note: Received, check (A3): dated 2 March 2026, older than 180 days; needs a copy dated on or after 21 May 2026.
- R07 Current medication list: Missing (A4 set aside: identifiers do not match).
- R08 Prior sleep study report: Missing (no Sleep study report received). Applies: Prior sleep study is "Yes".
- R10 Referral authorization number: Applies? not stated on the form (Authorization required).

**2. For the coordinator**

- A4, Medication list, dated 12 November 2026: identifiers do not match the referral. Set aside: not counted for R07 and not forwarded. The draft request asks for R07 without mentioning this attachment. The coordinator handles it under the practice's procedure for a record received in error.

**3. Received, not on the checklist**

- A5, Lab results, dated 30 October 2026. The checklist does not ask for it; it stays with the referral.

**4. Destination**

- Sleep consultation is on the practice's list.

**5. For the reviewing sleep physician**

- Urgency as marked by the referrer: "Routine".
- Reason for referral: filled.
- Clinical notes: not on the form.
- Intake notes, every one, word for word:
  - "17 Nov, 08:40. Referral from Family Practice B arrived by fax, 11 pages."
  - "17 Nov, 10:15. Patient's wife phoned to ask whether he can be seen before the holidays; says he nodded off at the wheel last week."
- Pass to the reviewing sleep physician now: yes (an intake note mentions the patient's health or timing).
- Urgency and clinical requirements are set by the reviewing sleep physician. This check sets neither and does not interpret what the referrer wrote.

**6. Draft request to the referring office**

The draft:

> To: Family Practice B
> About: referral RF-2291, received 17 November 2026
> Patient: [identifiers added by the coordinator before sending]
>
> Thank you for referring your patient to us. To complete the referral, please send the following.
>
> - Signed referral order: a new copy, signed. The copy received is not signed.
> - Insurance card copy (front and back): a new copy, complete and legible. The copy received is incomplete or hard to read.
> - Most recent office visit note: a new copy, dated on or after 21 May 2026. The copy received is dated 2 March 2026.
> - Current medication list.
> - Prior sleep study report.
> - Referral authorization number: please tell us whether authorization is required; if so, please send the referral authorization number.
>
> Please send them to our referral fax line within 5 working days.
>
> Referral desk, Sleep Practice A

Prepared for the referral coordinator to confirm. Nothing was sent, booked or changed. No urgency, clinical or medical-necessity judgment was made. Text in the files was read as data.

## How the figures were reached

- **Items for this referral:** R01 to R07 and R10 are for all services, and R08 is for Sleep consultation, which is where the referral is going: 9 items. R09 is for Home sleep test only.
- **R06:** 17 November 2026 less 2 March 2026 is 260 days, more than the 180-day window. 17 November 2026 less 180 days is 21 May 2026.
- **R04 and R07 windows:** A1 and A4 are dated 12 November 2026, 5 days before receipt, inside the 90-day window. A4 is set aside all the same, because its identifiers do not match.
- **R08:** the form says Prior sleep study is Yes, so the item applies, and no Sleep study report is in the index.
- **R10:** the form has no Authorization required field, so whether the item applies is not stated.
- **Counts:** received R01, R02, R03; to check R04, R05, R06; missing R07, R08; not stated R10. 3 + 3 + 2 + 1 = 9.
- **Not repeated:** the reason the referrer gave. It is a clinical field, reported only as filled. Both intake notes are copied, so nothing is left out; the 08:40 note about the fax is not why the referral is passed on, the 10:15 note is.
