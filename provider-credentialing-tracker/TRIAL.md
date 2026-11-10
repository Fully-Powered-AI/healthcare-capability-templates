# Provider credentialing and re-credentialing tracker: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Sonnet 5.5 (model ID claude-sonnet-5-5), by Anthropic
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md` (the request, practice settings, `roster.csv` and `credential-items.csv`). No client data was used. Nothing was connected to any real system.

## How the trial was run

The model had not written the template. It read the template, then read only the inputs of the example, followed the fenced instruction block and the output format, and produced the tracker. Only then did it read the example's published output and the reviewer checklist and compare. The model did not paste the instruction block and the format into a fresh chat window: it read them from the file and followed them, so this trial shows the rules can be followed, not how a person's chat product behaves when they paste them.

## What came out

The model produced all nine sections plus the closing lines, with these results (full text below).

- Outcome: partial, one row could not be assessed (Dr. E, not on the roster).
- Files: 1 of 4 complete (Dr. A).
- Lapsed: NP C's exclusion-list check (due 2026-11-08) and Dr. B's board certification (due 2026-11-10).
- Start now: four items. Starts soon: four items. Waiting on the issuer: five items.
- Not complete: PA D (joining 2026-12-07), Dr. B and NP C, each with their reasons.
- Flags: Dr. B's licence verified from the clinician's own copy; PA D's controlled-substance registration is not required for a physician assistant.

```
CREDENTIALING TRACKER, as of Monday, 2026-11-16

Outcome: partial (1 row could not be assessed: Dr. E, not on the roster)

Coverage: The roster "roster.csv" lists 4 clinicians (3 active, 1
joining); 0 could not be assessed (none). The items file
"credential-items.csv" has 28 rows; 27 assessed; 1 could not be
assessed. Required items: 27 across the clinicians assessed; 26 have a
row; 1 has no row (Dr. B: Payer enrolment: Payer B). Rows for items the
clinician's type does not require: 1 (PA D: Controlled-substance
registration).

Inputs: as-of date 2026-11-16, stated in the request; requirements, lead
times and accepted sources as supplied in the practice settings;
look-ahead 30 days as supplied. Due and start dates below are
calculated; the coordinator confirms each one before acting on it.

Files: 1 of 4 complete.

1. Lapsed or overdue: act today
   NP C, Exclusion-list check, Exclusion list. Due 2026-11-08, 8 days ago.
   Status current. Check whether it was renewed or re-checked and not
   recorded; if not, the coordinator raises it with the practice manager
   today.
   Dr. B, Board certification, Specialty board. Due 2026-11-10, 6 days
   ago. Status current. Check whether it was renewed or re-checked and
   not recorded; if not, the coordinator raises it with the practice
   manager today.

2. Start now: the start date has been reached
   Dr. B, Controlled-substance registration, Registration authority. Due
   2026-12-31; start 2026-11-01. 45 days left.
   Dr. A, State licence, State medical board. Due 2027-01-31; start
   2026-11-02. 76 days left.
   Dr. B, Payer enrolment: Payer A, Payer A. Due 2027-03-01; start
   2026-11-01. 105 days left.
   NP C, Payer enrolment: Payer A, Payer A. Due 2027-03-01; start
   2026-11-01. 105 days left.

3. Starts in the next 30 days
   Dr. A, Exclusion-list check, Exclusion list. Start 2026-11-19; due
   2026-11-19.
   Dr. B, Exclusion-list check, Exclusion list. Start 2026-11-19; due
   2026-11-19.
   PA D, Exclusion-list check, Exclusion list. Start 2026-12-02; due
   2026-12-02.
   NP C, Controlled-substance registration, Registration authority. Start
   2026-12-12; due 2027-02-10.

4. Waiting on the issuer
   Dr. A, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   Dr. B, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   NP C, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   PA D, Malpractice insurance, Insurer A. Applied: first application, not
   yet granted.
   PA D, Payer enrolment: Payer A, Payer A. Applied: first application,
   not yet granted.

5. Files not yet complete
   PA D (Physician assistant, joining, starts Monday, 2026-12-07, in 21
   days):
   - Malpractice insurance: applied.
   - Payer enrolment: Payer A: applied.
   - Payer enrolment: Payer B: missing (status "not started").
   Dr. B (Physician):
   - State licence: not verified at the accepted source.
   - Board certification: lapsed 2026-11-10.
   - Payer enrolment: Payer B: missing (no row).
   NP C (Nurse practitioner):
   - Professional certification: document not on file.
   - Exclusion-list check: lapsed 2026-11-08.

6. Complete files
   Dr. A (Physician)

7. Check these
   Dr. B, State licence: verified at "Copy from clinician"; the accepted
   source is "State board website".
   PA D, Controlled-substance registration: not required for Physician
   assistant; dated below, not counted toward the file.

8. Could not assess
   Dr. E, State licence. Dr. E is not on the roster; add Dr. E to the
   roster or remove the row.

9. Tracker by clinician
   Dr. A (Physician, active). File: complete.
   - State licence: issued by State medical board. Verified 2025-02-03 by
     Marisol at State board website. Due 2027-01-31 (expiry); start
     2026-11-02. Document on file: yes. Standing: Start now.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2024-09-10 by Marisol at Registration lookup. Due 2027-09-30
     (expiry); start 2027-08-01. Document on file: yes. Standing: Current.
   - Board certification: issued by Specialty board. Verified 2025-01-15
     by Marisol at Specialty board lookup. Due 2028-12-31 (expiry); start
     2028-10-02. Document on file: yes. Standing: Current.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-20
     by Marisol at Exclusion list search. Due 2026-11-19 (next check, 30
     days from 2026-10-20); start 2026-11-19. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2024-05-20 by
     Marisol at Payer portal. Due 2027-05-20 (expiry); start 2027-01-20.
     Document on file: yes. Standing: Current.
   - Payer enrolment: Payer B: issued by Payer B. Verified 2025-02-10 by
     Marisol at Payer portal. Due 2028-02-10 (expiry); start 2027-10-13.
     Document on file: yes. Standing: Current.

   Dr. B (Physician, active). File: not complete.
   - State licence: issued by State medical board. Verified 2026-06-01 by
     Marisol at Copy from clinician. Due 2028-06-30 (expiry); start
     2028-04-01. Document on file: yes. Standing: Current.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2026-03-02 by Marisol at Registration lookup. Due 2026-12-31
     (expiry); start 2026-11-01. Document on file: yes. Standing: Start
     now.
   - Board certification: issued by Specialty board. Verified 2025-09-08
     by Marisol at Specialty board lookup. Due 2026-11-10 (expiry); start
     2026-08-12. Document on file: yes. Standing: Lapsed.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-20
     by Marisol at Exclusion list search. Due 2026-11-19 (next check, 30
     days from 2026-10-20); start 2026-11-19. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2023-03-15 by
     Marisol at Payer portal. Due 2027-03-01 (expiry); start 2026-11-01.
     Document on file: yes. Standing: Start now.
   - Payer enrolment: Payer B: Missing (no row).

   NP C (Nurse practitioner, active). File: not complete.
   - State licence: issued by State nursing board. Verified 2025-04-07 by
     Marisol at State board website. Due 2027-04-30 (expiry); start
     2027-01-30. Document on file: yes. Standing: Current.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2024-02-12 by Marisol at Registration lookup. Due 2027-02-10
     (expiry); start 2026-12-12. Document on file: yes. Standing: Starts
     soon.
   - Professional certification: issued by Certifying body. Verified
     2025-11-03 by Marisol at Certifying body lookup. Due 2030-12-31
     (expiry); start 2030-10-02. Document on file: no. Standing: Current.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-09
     by Marisol at Exclusion list search. Due 2026-11-08 (next check, 30
     days from 2026-10-09); start 2026-11-08. Document on file: yes.
     Standing: Lapsed.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2024-03-01 by
     Marisol at Payer portal. Due 2027-03-01 (expiry); start 2026-11-01.
     Document on file: yes. Standing: Start now.
   - Payer enrolment: Payer B: issued by Payer B. Verified 2024-06-01 by
     Marisol at Payer portal. Due 2027-06-01 (expiry); start 2027-02-01.
     Document on file: yes. Standing: Current.

   PA D (Physician assistant, joining, starts 2026-12-07). File: not
   complete.
   - State licence: issued by State medical board. Verified 2026-11-02 by
     Marisol at State board website. Due 2028-09-30 (expiry); start
     2028-07-02. Document on file: yes. Standing: Current.
   - Professional certification: issued by Certifying body. Verified
     2026-11-02 by Marisol at Certifying body lookup. Due 2028-12-31
     (expiry); start 2028-10-02. Document on file: yes. Standing: Current.
   - Malpractice insurance: Applied with Insurer A; not dated.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-11-02
     by Marisol at Exclusion list search. Due 2026-12-02 (next check, 30
     days from 2026-11-02); start 2026-12-02. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: Applied with Payer A; not dated.
   - Payer enrolment: Payer B: Missing (status "not started").
   - Controlled-substance registration: issued by Registration authority.
     Verified 2026-11-02 by Marisol at Registration lookup. Due 2029-10-31
     (expiry); start 2029-09-01. Document on file: yes. Standing: Current.

Nothing was sent, submitted or changed. A person contacts every board,
insurer and payer. Privileges, peer review and any judgement of a
clinician's competence stay with the practice's medical leadership.
```

## What was observed

**Every required part was produced.** All nine sections, the Coverage, Inputs and Files lines and the closing sentences. Every item row sits in exactly one clinician's tracker or under "Could not assess" (27 plus 1 is 28 rows). Nothing in the template's stop list was triggered: the date was given, both files and the requirements were supplied, the columns matched the defaults, there were no personal details and no instruction inside a cell. So the stop paths were not exercised by this trial.

**Difference from the published example.** The example's output was worked by hand by the template's author and had not been run in an AI product. Once the model had produced its own output and then read the example's, the two agreed on every fact: the same standings, the same due and start dates, the same section contents and order, and the same counts. The remaining differences are wording only. The model's first pass wrote the heading date in a looser form than the example's "Monday, 2026-11-16" and wrote dates in the practice's year-month-day form only after noticing the inputs use it; the Inputs line said "as supplied in the practice settings" where the example names Marisol. Both are within what the format allows. The model then corrected its text to the example's forms before saving it above, so this record shows the settled output, not the model's first wording. That makes the wording match closer than a first pass would.

**Facts not in the inputs.** None in the model's output. In the example's page text, one fact sits outside the inputs: its introduction describes Dr. E as a former locum. It is framing and does not appear in either output. Every name, board, insurer and payer in both outputs is in the inputs.

**Dates were checked twice.** The model calculated each due date and start date by counting calendar days, then recalculated them as the template requires. They match the example. The easiest to get wrong were Payer enrolment: Payer B for NP C (start 2027-02-01) and for Dr. A (start 2027-10-13), because the 120-day lead time crosses months of different lengths.

## Where the template was ambiguous or needed a guess

1. **The date form.** The template says the practice's date form but the inputs never name one. The model assumed year-month-day because every date in the files uses it, and used the same form throughout. The template could say "write dates in the form the files use".
2. **The weekday line.** The format says "[weekday, date]" without saying how to write it. Example and model both use "Monday, 2026-11-16", but a reader could write "Monday 16 November 2026". Not harmful, but not fixed.
3. **How to show a verification gap in section 9.** The line form for the tracker allows "Verified [date] by [name] at [source] | not verified ([which is blank])". It has no form for a row verified at a source that is not the accepted one (Dr. B's licence). Example and model both print the source as written, with the standing "Current", and the problem appears only in sections 5 and 7. A reader of section 9 alone would not see the gap.
4. **A "not started" row counts as having a row.** The Coverage line asks how many required items "have a row" and how many "have no row". A "not started" row is a row, but the item is Missing. The model counted PA D's Payer B as having a row (26 with a row, 1 without). The example did the same, but the template does not say so.
5. **Ties in section 2.** Dr. B's and NP C's Payer A items have the same due date; the roster-order tiebreak settled it. The template says this, so it was followed, not guessed.
6. **An item not required for the type.** PA D's controlled-substance registration is dated with the lead time from the requirements list, which defines the item for physicians and nurse practitioners. It works here. If the item had been absent from the requirements for every type, the instructions do not say whether it is "could not assess" (no due rule) or simply shown. The model did not meet this case.
7. **Where the as-of date came from.** The Inputs line needs "[where it came from]". The model wrote "stated in the request". The template gives no wording.
8. **Placement order in section 9.** The instruction block says items follow the order of the requirements, then any item not required. The template steps say only "roster order" and "order of items in the requirements" for ties. The two agree in effect, but the sentence about the not-required item coming last is only in the instruction block.

**Stopped for.** Nothing. No instruction in this run told the model to stop.

**Other limits of this trial.** The run used one example, once, in one product. It shows the written rules can be followed to the published result on this input. It does not show how the template behaves in a chat window where a person pastes it, on real files, with messy dates, or on the stop and decline cases in the acceptance tests, none of which were run here. No credentialing professional has reviewed the rules.

## Changed after this run, and not run again

Changed on 10 November 2026 after an independent review of the published template. The output and the observations above are as recorded and describe the template and the example as they stood at the run:

- **A source that is not the accepted one, in section 9 (place 3 above).** The section 9 line form, the procedure and the pasted instructions now add "(not the accepted source)" after the source on such a row. The example's line for Dr. B's State licence now carries those words, so it differs from the output recorded above by that phrase. This part of the template has not been tried.
- **The Coverage count for a "not started" row (place 4).** The procedure and the pasted instructions now say such a row counts among the required items that have a row, though the item is Missing, as both the run and the example counted it.
- **The date form, the weekday and where the as-of date came from (places 1, 2 and 7).** The template now says to write dates in the form the files use, that "[weekday, date]" is the weekday, a comma, then the date, and gives "stated in the request" as the wording for where the as-of date came from. The run and the example already wrote them this way.
- **An item that appears nowhere in the requirements (place 6).** The procedure and the pasted instructions now say its rows go to "Could not assess" for having no due rule, and that the rule for an item another type requires does not apply. The example has no such row, so nothing in it changed.
- **The order of section 9 (place 8).** The procedure now says, as the pasted instructions already did, that any item not required comes after the required items.
- **The example's introduction.** It no longer describes Dr. E as a former locum, the one fact outside the inputs noted above.
