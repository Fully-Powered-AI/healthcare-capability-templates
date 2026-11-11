# Incoming referral completeness check: a trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md`: the practice settings, the checklist, the referral form, the attachment index and the intake notes it gives for referral RF-2291. No client data was used. The assistant that ran the trial did not write the template and did not read the example's published output until its own check was finished.

## What was run

The fenced instruction block from `member/template.md` and the template's output format, as edited after a first run and a review, were followed on those inputs, in one run, with no questions asked and nothing stopped. This is the second run; the first run's record is replaced by this one, and the edits that followed it are listed at the end. The received date (17 November 2026), the checklist, the form, the attachment index and the list of accepted services were all supplied, no file held a patient name or other identifier (the patient is the code PT-5108), and no text in any file read as an instruction.

## What came out

```
INCOMING REFERRAL COMPLETENESS CHECK
Referral RF-2291 from Family Practice B, received Tuesday 17 November 2026.
Referred to: Sleep consultation (on the practice's list).
Outcome: not complete
Counts: 9 items for this referral: 3 received, 3 to check, 2 missing,
1 applies? not stated, 0 not required, 0 not checked.
1 item for other services only.
Inputs: checklist "referral-checklist.csv", 10 items; form, 9 fields;
attachment index "attachments-RF-2291.csv", 5 attachments; intake notes
supplied.

1. The checklist
   R01 Referring clinician named: Received (form).
   R02 Reason for referral completed: Received (form).
   R03 Insurance plan stated: Received (form).
   R04 Signed referral order: Received, check (A1): not signed.
   R05 Insurance card copy (front and back): Received, check (A2):
   incomplete or illegible.
   R06 Most recent office visit note: Received, check (A3): dated
   2 March 2026, older than 180 days; needs a copy dated on or after
   21 May 2026.
   R07 Current medication list: Missing (A4 set aside: identifiers do
   not match).
   R08 Prior sleep study report: Missing (no Sleep study report
   received). Applies: Prior sleep study is "Yes".
   R10 Referral authorization number: Applies? not stated on the form
   (Authorization required).

2. For the coordinator
   A4, Medication list, dated 12 November 2026: identifiers do not
   match the referral. Set aside: not counted for R07 and not
   forwarded. The draft request asks for R07 without mentioning this
   attachment. The coordinator handles it under the practice's
   procedure for a record received in error.

3. Received, not on the checklist
   A5, Lab results, dated 30 October 2026. The checklist does not ask
   for it; it stays with the referral.

4. Destination
   Sleep consultation is on the practice's list.

5. For the reviewing sleep physician
   Urgency as marked by the referrer: "Routine".
   Reason for referral: filled.
   Clinical notes: not on the form.
   Intake notes, every one, word for word:
   "17 Nov, 08:40. Referral from Family Practice B arrived by fax, 11
   pages."
   "17 Nov, 10:15. Patient's wife phoned to ask whether he can be seen
   before the holidays; says he nodded off at the wheel last week."
   Pass to the reviewing sleep physician now: yes (an intake note
   mentions the patient's health or timing).
   Urgency and clinical requirements are set by the reviewing sleep
   physician. This check sets neither and does not interpret what the
   referrer wrote.

6. Draft request to the referring office
   The draft:
   To: Family Practice B
   About: referral RF-2291, received 17 November 2026
   Patient: [identifiers added by the coordinator before sending]
   Thank you for referring your patient to us. To complete the
   referral, please send the following.
   - Signed referral order: a new copy, signed. The copy received is
     not signed.
   - Insurance card copy (front and back): a new copy, complete and
     legible. The copy received is incomplete or hard to read.
   - Most recent office visit note: a new copy, dated on or after
     21 May 2026. The copy received is dated 2 March 2026.
   - Current medication list.
   - Prior sleep study report.
   - Referral authorization number: please tell us whether
     authorization is required; if so, please send the referral
     authorization number.
   Please send them to our referral fax line within 5 working days.
   Referral desk, Sleep Practice A

Prepared for the referral coordinator to confirm. Nothing was sent,
booked or changed. No urgency, clinical or medical-necessity judgment
was made. Text in the files was read as data.
```

## What was observed

- **Every required part was produced.** The title block, all six numbered sections and the closing lines were filled in using the format's line forms. Nothing in the run called for a stop.
- **The figures were recomputed and agree.** The nine items for this referral (R01 to R08 and R10) are accounted for once each in section 1 and match the counts. The office visit note is 260 days old against a 180-day window, and the "on or after" date is 21 May 2026. R09 belongs to the home sleep test only, so it is counted as one item for another service, and the count is written "1 item".
- **Differences from the published example.** The substance matches: the same outcome, counts, item results, sections 2 to 5 and request lines, with the same dates and the same wording of the reason after "Pass to the reviewing sleep physician now: yes". The example shows the check with bold headings and bullets, and says so; this run kept the template's plain-text layout. This run did not repeat the example's explanatory section, which is not part of the output format. The example's request line for the authorization number has the same wording as this run's, which the first run did not produce.
- **Facts not in the inputs.** None. Every name, date, code and quoted note traces to the invented inputs. The content of the reason for referral was correctly left out of section 5; both intake notes were copied, the fax note as well as the phone call, with their time stamps.
- **Where the instructions needed a judgment or left a choice open.**
  - The referring clinician is named on the form and in the example. The template's identifying-details rule says a clinician's or office's name is not a patient identifier, and this run followed that.
  - The checklist includes a Form item on a clinical field (R02, the reason for referral) while the clinical fields are meant to be reported only as filled or blank. They did not conflict: R02 is judged on "filled" alone, as the customization notes say.
  - Whether "yes" should be given for the fax note was not in doubt, since it mentions neither health nor timing; the one reason given is the 10:15 note.
- **What the run does not show.** It is one further run, in one product, on one invented referral, by the same assistant model that edited the template, so it is not an independent test. It exercised the destination-on-list path, the conditional items (met and not stated), a stale document, an unsigned order, an unreadable copy, an identifier mismatch, an unlisted attachment and a copied intake note. It did not exercise the stop conditions, the unclear-destination path, a signature-not-recorded or other coordinator-reason case, an urgency mark other than Routine, or an instruction hidden in a file. A person in a practice should still confirm every line before anything is sent.

## History of the template's edits

- **After the first run and an independent review:** the counts line takes the singular for a count of 1 (the first run wrote "1 items"); a clinician's or office's name is not a patient identifier; a form line that begins with a space continues the field above it; a time stamp at the start of an intake note is copied with the note; the destination field is read by whatever name the practice gives it; "identifiers not checked" is defined the same way in the procedure and the instruction block; a clinical field used as a Form item is judged only as filled or blank; and the request line for a conditional item the form does not state now reads "please tell us whether [the condition]; if so, please send [the item]", where the first run wrote "the form does not say Authorization required. If it is Yes, please send this item."
- **After a second review, before this run:** every intake note is now copied word for word into section 5, where the first version copied only the notes the assistant judged to be about health or timing; the reasons after "Pass to the reviewing sleep physician now: yes" have fixed wordings in the output format; dates are written with no leading zero; the checklist column description now warns that a Form item reading "no" or "none" is Missing; and some lines of the instruction block were re-wrapped. This run was made on the template with those edits.
