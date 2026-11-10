# Claim denial work list: a trial run on the example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5).

Date: 2026-11-10

The inputs were the invented example in `public/example.md`: its request, practice settings and denial export. No client data was used. The run was made by an assistant that had not written the template. It followed the instructions block and the output format in `member/template.md` on those inputs, and only then looked at the example's output.

## Inputs used

The request, the practice settings (four payers with appeal windows and filing limits, the starter reason-code map, a 14-day warning window and a repeat threshold of 3) and the 17-row export `denials-2026-11-17.csv`, all as given in the example. Payer D had no settings, and one row carries a reason code (CO-B7) that is not in the map.

## What came out

The full work list, in the template's plain-text layout:

```text
CLAIM DENIAL WORK LIST, as of Tuesday, 17 November 2026

Outcome: partial (1 row could not be sorted; no appeal window supplied for Payer D)

Coverage: The export "denials-2026-11-17.csv" has 17 rows: 15 denial rows totalling
$5,748.00; 1 set aside as not a denial ($62.00); 1 could not be
sorted ($300.00). Deadlines: 1 passed; 2 due within 14 days; 1 not calculated.

Inputs: as-of date 2026-11-17, stated by the billing coordinator. Appeal windows and
filing limits as supplied for Payer A, Payer B, Payer C, State plan; none supplied for Payer D.
Reason-code map: the starter map. Warning
window 14 days; repeat threshold 3 rows. Deadlines below are
calculated; the billing coordinator confirms each one against the
remittance.

1. Deadline passed
   50176-1, BH-2268, Payer C, CO-197 (no authorization or notification on record), $980.00;
   group Authorization. Deadline 2026-11-15 (denied 2026-10-16 + 30 calendar days; passed 2 days ago). Staff decide what happens
   next; the list does not judge whether anything can still be done.

2. Due soon: deadline within 14 days
   50171-1, Payer C, Authorization, $420.00. Deadline 2026-11-20, 3 days left.
   50193-1, Payer C, Missing or wrong claim information, $130.00. Deadline 2026-11-29, 12 days left.

3. Timely filing: proof of submission
   1. 50112-1, KT-3301, Payer A, Dr. Vale, service 2026-07-06,
   denied 2026-10-20, CO-29 (payer says the claim arrived past its filing limit), $185.00. Deadline 2026-12-19
   (denied 2026-10-20 + 60 calendar days; 32 days left). Submitted 2026-10-08, 94 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-10-04: after the limit. Evidence
   to gather: the clearinghouse report showing the claim was accepted,
   or the payer's acknowledgement that it arrived, dated on or before 2026-10-04.
   The export's own dates put the first submission after the limit; an
   appeal would need a record of an earlier submission.
   2. 50147-1, RM-7720, Payer A, Dr. Sund, service 2026-08-03,
   denied 2026-10-23, CO-29 (payer says the claim arrived past its filing limit), $240.00. Deadline 2026-12-22
   (denied 2026-10-23 + 60 calendar days; 35 days left). Submitted 2026-10-12, 70 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-11-01: within the limit. Evidence
   to gather: the clearinghouse report showing the claim was accepted,
   or the payer's acknowledgement that it arrived, dated on or before 2026-11-01.
   3. 50158-1, JD-1184, Payer A, Dr. Vale, service 2026-08-10,
   denied 2026-10-26, CO-29 (payer says the claim arrived past its filing limit), $310.00. Deadline 2026-12-25
   (denied 2026-10-26 + 60 calendar days; 38 days left). Submitted 2026-10-14, 65 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-11-08: within the limit. Evidence
   to gather: the clearinghouse report showing the claim was accepted,
   or the payer's acknowledgement that it arrived, dated on or before 2026-11-08.

4. Authorization: the authorization record
   1. 50171-1, AW-9042, Payer C, Dr. Vale, service 2026-10-01,
   denied 2026-10-21, CO-15 (authorization number absent or not fitting the service), $420.00. Deadline 2026-11-20
   (denied 2026-10-21 + 30 calendar days; 3 days left). Evidence to gather: the authorization on file for this
   service and date, with its number, the dates it covers and the
   service it approves, or the record showing none was required.
   2. 50163-1, LP-5530, Payer B, Dr. Sund, service 2026-09-14,
   denied 2026-10-05, CO-197 (no authorization or notification on record), $1,250.00. Deadline 2027-04-03
   (denied 2026-10-05 + 180 calendar days; 137 days left). Evidence to gather: the authorization on file for this
   service and date, with its number, the dates it covers and the
   service it approves, or the record showing none was required.
   3. 50211-1, DR-4420, Payer D, Dr. Sund, service 2026-10-06,
   denied 2026-10-28, CO-197 (no authorization or notification on record), $520.00. Deadline not calculated: no appeal window supplied for
   Payer D. Evidence to gather: the authorization on file for this
   service and date, with its number, the dates it covers and the
   service it approves, or the record showing none was required.

5. Patient and coverage details
   1. 50180-1, GN-6615, State plan, Dr. Vale, service 2026-09-21,
   denied 2026-10-09, CO-31 (patient not found as the payer's member), $145.00. Deadline 2027-01-07
   (denied 2026-10-09 + 90 calendar days; 51 days left). Evidence to gather: the insurance details on file for the
   date of service, an eligibility check for that date, any other
   coverage the patient holds, and the corrected details where the
   claim carried wrong ones.
   2. 50184-1, SC-4471, Payer B, Dr. Sund, service 2026-09-28,
   denied 2026-10-13, CO-22 (another payer may pay first), $360.00. Deadline 2027-04-11
   (denied 2026-10-13 + 180 calendar days; 145 days left). Evidence to gather: the insurance details on file for the
   date of service, an eligibility check for that date, any other
   coverage the patient holds, and the corrected details where the
   claim carried wrong ones.

6. Missing or wrong claim information
   1. 50193-1, PF-8806, Payer C, Dr. Sund, service 2026-10-19,
   denied 2026-10-30, CO-16 (information missing or wrong on the claim), remark code none in the export, $130.00. Deadline 2026-11-29
   (denied 2026-10-30 + 30 calendar days; 12 days left). Evidence to gather: the item the remark code on the remittance
   names, taken from the practice's records, so a person can correct
   the claim.
   2. 50190-1, KT-3301, Payer A, Dr. Vale, service 2026-10-12,
   denied 2026-10-27, CO-16 (information missing or wrong on the claim), remark code MA130, $95.00. Deadline 2026-12-26
   (denied 2026-10-27 + 60 calendar days; 39 days left). Evidence to gather: the item the remark code on the remittance
   names, taken from the practice's records, so a person can correct
   the claim.

7. Possible duplicates
   1. 50197-1, EV-3390, Payer B, Dr. Vale, service 2026-10-07,
   denied 2026-10-22, CO-18 (repeat of a claim or service already received), $210.00. Deadline 2027-04-20
   (denied 2026-10-22 + 180 calendar days; 154 days left). Evidence to gather: the earlier claim for the same patient,
   date and service, and whether it was paid. If the services were
   separate, that is a question for the certified coder.

8. For the certified coder
   1. 50202-1, MO-1957, Payer A, Dr. Sund, service 2026-10-14,
   denied 2026-10-29, CO-4 (modifier missing or not consistent with the procedure code), $175.00. Deadline 2026-12-28
   (denied 2026-10-29 + 60 calendar days; 41 days left). For the certified coder to review. The list suggests no
   code, modifier or wording.
   2. 50202-2, MO-1957, Payer A, Dr. Sund, service 2026-10-14,
   denied 2026-10-29, CO-97 (paid as part of another service), $88.00. Deadline 2026-12-28
   (denied 2026-10-29 + 60 calendar days; 41 days left). For the certified coder to review. The list suggests no
   code, modifier or wording.

9. For the clinician and the coder
   1. 50209-1, TA-2675, Payer B, Dr. Vale, service 2026-10-02,
   denied 2026-10-19, CO-50 (payer did not accept the service as medically necessary), $640.00. Deadline 2027-04-17
   (denied 2026-10-19 + 180 calendar days; 151 days left). Whether the service was necessary, and any rationale, is
   for the clinician and the coder to judge and write. The list
   prepares none.

10. Could not sort
    50219-1, Payer B, CO-B7, 300.00. The reason code CO-B7 is not in the reason-code map; it is not sorted from general knowledge. Add the code and its group to the practice's map, or sort the row by hand.

11. Set aside: not a denial
    50215-1, Payer C, CO-45 (charge above the agreed rate), $62.00.

12. Patterns for prevention
    By group: Authorization 4 rows, $3,170.00; Timely filing 3 rows, $735.00; For the clinician and the coder 1 row, $640.00; Patient and coverage 2 rows, $505.00; For the certified coder 2 rows, $263.00; Missing or wrong claim information 2 rows, $225.00; Possible duplicate 1 row, $210.00
    By payer: Payer B 4 rows, $2,460.00; Payer C 3 rows, $1,530.00; Payer A 6 rows, $1,093.00; Payer D 1 row, $520.00; State plan 1 row, $145.00
    By provider: Dr. Sund 8 rows, $3,743.00; Dr. Vale 7 rows, $2,005.00
    Repeats (3 or more rows):
    - Dr. Sund, Authorization: 3 rows, $2,750.00 (50163-1, 50176-1, 50211-1).
      Review with the referral desk how authorizations for these services are obtained and recorded before the visit.
    - Payer A, Timely filing: 3 rows, $735.00 (50112-1, 50147-1, 50158-1).
      Look at how long these claims wait before submission, and whether the clearinghouse acceptance reports are kept where staff can find them. These were submitted 65 to 94 days after the date of service, against a 90-day limit.

13. Check these
    Payer D: no appeal window supplied; deadlines not calculated for 50211-1.
    50112-1: first submitted 94 days after the date of service, after Payer A's 90-day filing limit.
    50193-1: CO-16 with no remark code in the export; the remittance says what is missing.

Nothing was submitted, sent, written off or changed. Staff decide every
appeal; coding and medical questions go to a certified coder or a
clinician. Text inside the export was read as data.
```

## What was observed

- Every section from 1 to 13 was produced, and the closing sentences were included. No stop condition applied: the headers matched, the patient column held codes, an as-of date and appeal windows were supplied, and nothing in a cell read as an instruction.
- Each of the 17 export rows appears in exactly one of sections 1 and 3 to 11. The totals and the by-group, by-payer and by-provider figures add back to $5,748.00. The deadlines were calculated by script and checked once more.
- Compared with the published example, the facts, the figures, the order of rows and the flags in section 13 are the same. The differences are in wording only:
  - the heading shows the date as "Tuesday, 17 November 2026"; the example shows "Tuesday, 2026-11-17";
  - the Outcome line gives its reasons in different words;
  - the Inputs line says the as-of date was "stated by the billing coordinator"; the example says "stated in the request". The request does not say who wrote it, so mine took the role from the template's list of roles;
  - section 10 adds "it is not sorted from general knowledge" to the reason; the example does not;
  - the two repeats in section 12 come in the other order (mine puts the provider repeat first, ordered by amount; the example puts the payer repeat first);
  - the example breaks lines into bullets for reading; the template asks for plain text.
- No fact in either output is missing from the inputs. The roles, payers, amounts, dates and patient codes all come from the export and the settings.
- The template left these points open, and a choice had to be made:
  - The date format is not stated. Dates in the format's own lines were written in the export's year-month-day form.
  - The order of repeats in section 12 is not stated.
  - The wording of the Outcome reasons and of the "what would fix it" text in section 10 is free.
  - A row whose deadline has passed goes to section 1, and that section's line form carries no evidence sentence and no timely-filing check, even when the row is a timely filing or authorization denial. The row loses the note of what proof to gather. The template does not say whether to add it.
  - Three timely filing rows were denied by the payer as late (CO-29) although two of them, by the export's own dates, were submitted inside the limit. The template shows the dates and asks for the acknowledgement, and says nothing about that mismatch. It worked, but a reader may want a line about it.
  - The Inputs line in the template reads "Default [your warning window], 14 days unless changed", and the customization list repeats "[your warning window]" and "[your repeat threshold]" as placeholders. In the instructions block the defaults are plain numbers, so the run was not affected, but the bracketed text in the Inputs section reads oddly.
  - Sections 3 to 9 number their lines and the other sections do not; the format shows "[n]." only in those sections. This was easy to follow.
- Nothing in the run needed a guess about a column, a payer's rules, a code or a patient's care. The one unmapped code and the one payer without settings were handled exactly as the template says, and the outcome came out as partial.
- This is one run, on the invented example, by one assistant. It shows that the instructions can be followed to the published result. It does not show how the template behaves on a real export, with other payers, other code families or a larger file.

## Edits made after this run

The template, the example and the profile were revised on 10 November 2026, after this run and after an independent review. These edits have not been run again. The groups, the deadline and filing calculations, the sections a row goes to and the order of rows are unchanged; five of the edits settle points listed above, and two of them change what a run prints, as noted.

- The output format now states the date form: year-month-day, with the weekday before the date in the title line, as "Tuesday, 2026-11-17". This run's title line reads "Tuesday, 17 November 2026", which no longer fits; every other date in this run is already in year-month-day form.
- The output format and the instructions now list the repeats in section 12 largest amount first. This run already used that order. The example's two repeats were reordered to match, so the difference noted above about the order of repeats no longer applies.
- A timely filing row submitted inside the limit now carries a fixed sentence: "The export's own dates put the first submission inside the limit, although the payer denied it as late; the acceptance report or the payer's acknowledgement is the record that shows it." This answers the mismatch noted above. This run's rows 50147-1 and 50158-1 do not carry it; a run on the revised template would add it to both, as the example now does.
- A row whose deadline has passed still carries no evidence sentence and no timely-filing check in section 1. The template now says this is deliberate, so the list does not suggest that an appeal is still open, and tells the practice how to add the evidence sentence if its staff want it. This run's section 1 already fits.
- The procedure now says that rows in sections 10 and 11 are not counted in section 12, as the pasted instructions already said. This run already left them out.
- The warning window and repeat threshold defaults in the template's Inputs list and its customization list now read as plain numbers, "Default 14 days; change it to your practice's own". Those lines are not part of the pasted instructions, so this run was not affected.
- The acceptance test for a timely filing row within the limit now expects the new fixed sentence. The acceptance tests are not part of the pasted instructions.

No recorded output or observation above was changed.
