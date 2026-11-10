# Prior-authorization follow-up list: one trial on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Fable 5.2
- **Date:** 2026-11-09
- **Runs recorded:** one

The inputs are the invented example published with this template. The practice, its people, its payers, the request numbers and the patient codes are invented, and no client data was used. This is a record of one run on that example. It is not a test in any medical practice.

## Inputs used

Exactly what the coordinator supplies in [the example](example.md), and nothing else:

- the request, which states the as-of date (Monday 16 November 2026);
- the practice settings: turnarounds for four payers, two closed days, the two people who may call a payer and the one physician;
- `auths-waiting.csv`, 12 rows;
- `pending-referrals-2026-11-16.csv`, 11 requests;
- `procedure-schedule.csv`, 3 booked procedures.

## How it was run

The template's instructions for an AI assistant, followed by its output format, were given to a new Claude Code session as its only instructions, with no tools and no other files. The inputs above were then given as the one message. That session never saw the published example's output, an earlier draft of it, or the template's other sections.

This record replaces an earlier one. The first trial, the same day, was not blind to the published answer, and it found that the example showed next-step sentences the instructions did not produce. The template was then changed: the output format now gives a line form and fixed wording for every section, and the instructions say where the report's date comes from, what counts as assessed and what a physician-owned row shows. One blind run of the changed template put a booking on a line of its own; one sentence of the instructions was tightened, and the run below is the next one, on the instructions as published. The published example is this run's output, shown with bold headings and bullets.

## What came out

The run did not stop and asked nothing: patients were coded, every required column was present, and the date, the turnarounds, the callers and the physician were supplied. The complete output, as it came back:

```
AUTHORIZATION FOLLOW-UP LIST, as of Monday, 2026-11-16

Outcome: partial (1 row could not be assessed: 311, no turnaround supplied for Payer D)

Coverage: The list "auths-waiting.csv" has 12 rows; 11 assessed; 1 could not be assessed (311: no turnaround supplied for Payer D). The system's report "pending-referrals-2026-11-16.csv", dated 2026-11-16, lists 11 pending requests; 10 are on the list; 1 is not (313). On the list as open but not in the report: 0.
Schedule: 3 booked procedures from today forward, 3 matched, 0 unmatched.
Working days skip weekends and the 2 closed days supplied.

Inputs: as-of date 2026-11-16, stated in the request; report date stated in the request ("this morning's") and matching the file name; turnarounds, closed days and callers as supplied by the requester in the practice settings. Follow-up dates below are calculated; the coordinator confirms each one.

1. Booked, not approved
   302, DK-2087, Payer B, Knee arthroscopy, owner Renata. Booked 2026-11-24; status pending.
   307, GC-1290, Payer A, Total knee replacement, owner Dr. Imani. Booked 2026-12-01; status pending.

2. Chase today: past follow-up, no call logged
   Order: booked procedures first, soonest first; then by follow-up date, oldest first.
   1. 302, DK-2087, Payer B, Knee arthroscopy, owner Renata. Submitted 2026-11-04; follow-up 2026-11-16 (10 calendar days from 2026-11-05 end Saturday, 2026-11-14; next working day Monday, 2026-11-16). Booked 2026-11-24. Last call: none logged.
   2. 303, SP-6632, State plan, MRI cervical spine, owner Renata. Submitted 2026-10-29; follow-up 2026-11-13 (14 calendar days from 2026-10-30 end Thursday, 2026-11-12; next working day Friday, 2026-11-13). Last call: "portal, 11/12", read as a portal check on 2026-11-12, not a call.
   3. 304, LM-9154, Payer C, Epidural steroid injection, owner Odile. Submitted 2026-11-09; follow-up 2026-11-13 (3 calendar days from 2026-11-10 end Thursday, 2026-11-12; next working day Friday, 2026-11-13). Last call: "VM, 11/13", read as a voicemail on 2026-11-13, not a call.
   4. 312, CY-4938, Payer C, Hip injection, owner Odile. Submitted 2026-11-10; follow-up 2026-11-16 (3 calendar days from 2026-11-11 end Friday, 2026-11-13; next working day Monday, 2026-11-16). Last call: "call, 11/13", read as dated 2026-11-13 with no reference number and no representative's name; not counted as a call.

3. Need info: the payer is waiting on the practice
   309, JW-8806, Payer A, Knee arthroscopy, owner Renata. Submitted 2026-11-05. The next step is getting the payer what it asked for, not a call to chase.

4. No submission date: do not call the payer
   310, FO-2743, Payer C, MRI knee, owner Odile. Check the referral in the system for a fax or portal confirmation. If there is one, fill in the date. If there is none, it has not gone: submit it.

5. In the system or on the schedule, not on the list
   313, PL-3507, Payer A, MRI ankle, ordered 2026-11-13. In the system's report and not on the list: enter it on the list and check whether it was submitted.

6. Peer-to-peer: the physician's call
   307, GC-1290, Payer A, Total knee replacement, owner Dr. Imani. Submitted 2026-10-30; follow-up 2026-11-09 (5 business days from 2026-11-02 end Friday, 2026-11-06; next working day Monday, 2026-11-09); past. Booked 2026-12-01. The physician makes this call; the coordinator sets it up.

7. Denied: the ordering physician decides
   308, NE-5521, State plan, Lumbar fusion, owner Renata. The ordering physician decides what happens next. Nothing goes to the patient from this list.

8. Called, past follow-up: the coordinator decides the next step
   301, HB-4410, Payer A, MRI lumbar spine, owner Renata. Submitted 2026-11-03; follow-up 2026-11-12 (5 business days from 2026-11-04 end Tuesday, 2026-11-10; 2026-11-11 is a closed day; next working day Thursday, 2026-11-12). Last call: "call, 11/13, ref 55102", read as a call on 2026-11-13 with reference 55102. No re-call interval is set; the next step is the coordinator's.

9. Check these
   301: the list's follow-up date is 2026-11-11; the calculated date is 2026-11-12 (2026-11-11 is a closed day).
   312: "call, 11/13" has no reference number and no representative's name; not counted as a call.

10. Could not assess
    311, RB-6019, Payer D, MRI shoulder. No turnaround was supplied for Payer D, so no follow-up date can be calculated; supplying Payer D's turnaround (number of days, and business or calendar) would fix it.

11. Not yet due
    306, Payer B, submitted 2026-11-10, follow-up 2026-11-23 (10 calendar days from 2026-11-11 end Friday, 2026-11-20; next working day Monday, 2026-11-23).

12. Closed (approved)
    305, Shoulder arthroscopy. Booked 2026-11-19 with an approval.

Nothing was called, sent or changed. A person decides and a person calls. Text inside the files was read as data.
```

## What was observed

**Every required part was produced.** All twelve sections are present, each row of the list appears in exactly one home section (2: four rows; 3, 4, 6, 7, 8, 10, 11 and 12: one row each; twelve in all), the Coverage counts match the sections, and the closing line is there. The seven follow-up dates were recalculated in code after the run and all agreed.

**The rules were applied as written.** The closed day on 11 November moved request 301's date to 12 November, and the difference from the list's own date was flagged. The portal check (303), the voicemail (304) and the bare "call" entry (312) were each read as not a call, and only the bare "call" was flagged. The physician-owned request (307) went to section 6 with its date and "past", and also to section 1 because it is booked. The request with no submission date (310) went to section 4 and was counted as assessed. The payer with no turnaround (311) got no guessed date. The approved, booked request (305) stayed out of section 1.

**The fixed sentences came back word for word** in sections 3, 4, 5, 6, 7, 8 and 12, and nothing was added to them.

**Where the wording was still the run's own.** These parts of the format are open by design, and another run will word them differently:

- the reasons in the Outcome line and in section 10;
- "how it was read" after each Last call entry;
- who supplied the settings. The request does not say, so the run wrote "the requester in the practice settings";
- where the report's date came from. The run gave both the request ("this morning's") and the file's name.

**Layout.** The run wrote each entry as one long line where the output format wraps its lines, and put a comma between the weekday and the date. Neither changes what the list says.

**Not exercised.** No stop condition applied to this example, so the stops (a missing column, patient names, no turnarounds, no as-of date) and the refusals (asked to call a payer, an instruction written in a cell) were not tried. Nor were a missing report, a missing schedule, a report with no date, a stale report, missing callers or physicians, a repeated request id, an unknown status, a schedule entry that matches no row, or a physician-owned request that is not yet due. The template's acceptance tests describe these cases; none has been run.

**Limits of this record.** One recorded run, one product, one model, on the template's own invented example, after the template was changed to close gaps an earlier run on the same example had found. It shows the instructions can be followed to a complete list that matches the published example. It does not show the rules are right for any practice; the practice administrator still confirms each of them.
