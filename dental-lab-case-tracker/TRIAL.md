# Dental lab case tracker: tried on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Opus 5.5 (model ID claude-opus-5-5)
- **Date:** 2026-11-10

The inputs were the invented example on the example page: the request, the office settings and the lab case list `lab-cases.csv` (14 rows, with a Shade column), for the invented office on Monday 16 November 2026. No client data was used. The tracker was prepared by following the instruction block and the output format in the template as they stand after the review edits listed at the end of this record. This run was not blind: the model had already read the example's published tracker while making those edits. The output below was saved as the run produced it, then compared with the example's tracker by script.

## What came out

```
DENTAL LAB CASE TRACKER, as of Monday, 2026-11-16

Outcome: partial (1 row could not be assessed: C-125)

Coverage: The lab case list "lab-cases.csv" has 14 rows; 13 assessed; 1
could not be assessed. Of those assessed: 6 at the lab; 6 received (1
waiting for the seating, 5 back and past their seating, or with none
booked); 1 cancelled and not tracked. Labs: 3 (Lab A, Lab B, Lab C).
Columns not read: Shade; their contents are not repeated.

Inputs: as-of date 2026-11-16, stated in the request; check-in 2 days as
supplied; look-ahead 7 days as supplied; quarter 2026-10-01 to
2026-12-31 by default, counted through 2026-11-16. Dates below are
calculated from the case list; the coordinator confirms each one with
the lab before acting on it.

1. Overdue from the lab: act today
   C-117, P-0718, Dr. K, Lab C, Crown. Sent 2026-10-27; lab due
   2026-11-10, 6 days ago. Seating 2026-11-12 has passed; the front
   desk rebooks the patient once the case is in. The coordinator calls
   the lab today.
   C-115, P-2231, Dr. M, Lab B, Partial denture. Sent 2026-10-26; lab
   due 2026-11-13, 3 days ago. Seating 2026-11-19; still kept if the
   case arrives by 2026-11-17. The coordinator calls the lab today.

2. Due back too late for the seating
   C-120, P-3390, Dr. K, Lab B, Crown. Lab due 2026-11-18; seating
   2026-11-18. It needs to arrive by 2026-11-16, 2 days before the
   lab's date. Ask the lab for an earlier date or move the seating; a
   person decides which.

3. At the lab with no seating booked
   C-121, P-0954, Dr. M, Lab C, Crown. Lab due 2026-11-19. No seating
   booked.

4. Due back in the next 7 days
   C-123, P-2610, Dr. K, Lab A, Veneers. Lab due 2026-11-20; seating
   2026-11-25.

5. On track
   C-124, P-1187, Dr. M, Lab B, Bridge. Lab due 2026-11-24; seating
   2026-11-30.

6. Back from the lab, waiting for the seating
   C-118, P-2875, Dr. K, Lab A, Crown. Received 2026-11-13; seating
   2026-11-20. The dentist looks it over before the seating.

7. Remakes sent this quarter
   C-118, Lab A, remake of C-109 (Lab A). Sent 2026-11-02; received
   2026-11-13. Reason as recorded: "Did not fit at the seating
   appointment; Dr. K asked for a remake".
   C-124, Lab B, remake of C-104 (Lab B). Sent 2026-11-10; at the lab,
   due 2026-11-24. Reason not recorded.

8. Each lab's record, 2026-10-01 to 2026-11-16
   Rows under "Could not assess" and cancelled rows are not counted.
   Lab A
   - Sent this quarter: 4.
   - Received this quarter: 3; on time 3; late 0 (none).
   - Average days from sent to received: 11.3, over 3 cases.
   - Out now: 1; past the lab's date 0 (none).
   - Remakes of its cases sent this quarter: 1 (C-118).
   Lab B
   - Sent this quarter: 4.
   - Received this quarter: 1; on time 0; late 1 (C-104 by 2 days).
   - Average days from sent to received: 16.0, over 1 case.
   - Out now: 3; past the lab's date 1 (C-115).
   - Remakes of its cases sent this quarter: 1 (C-124).
   Lab C
   - Sent this quarter: 3.
   - Received this quarter: 1; on time 0; late 1 (C-112 by 1 day).
   - Average days from sent to received: 15.0, over 1 case.
   - Out now: 2; past the lab's date 1 (C-117).
   - Remakes of its cases sent this quarter: 0 (none).

9. Check these
   C-124: remake with no reason recorded; the dentist states it.

10. Could not assess
   C-125. Status "on hold" is not one of at lab, received or cancelled;
   correct the status in the case list, then run the tracker again.

Nothing was sent, booked or changed. A person contacts every lab and
every patient. The treating dentist writes every prescription, chooses
shade and material, and judges the fit of the work; this tracker records
dates and the office's own words only.
```

## What was observed

- **Every required part was produced.** All ten sections, the Coverage, Inputs and Outcome lines and the closing lines are present. Every one of the 14 rows is in exactly one place, and the Coverage counts match the sections.
- **Nothing in the run called for a stop.** The as-of date was stated, no default column was missing, and the file held no personal details beyond the chart references. The one unreadable row (C-125, status "on hold") was set aside under section 10 and made the outcome partial, as the rules say.
- **The result matches the published example word for word.** A script found the same 637 words in the same order. The two differ only in where two entries break their lines: C-117 in section 1 and C-120 in section 2. No case placement, date, count, average or list order differs. No fact appears in either tracker that is not in the inputs. The Shade column was named and its contents not repeated.
- **Where the wording left room.** None of these changed the result here, but each could change it on other data:
  - The output format does not say where to break long lines, so a run's line breaks can differ from the example's, as they did here.
  - Section 7 now ends a quoted reason with a full stop outside the quotation marks. A recorded reason that itself ends with a full stop would print two. The example has none.
  - The format's "Ask the lab for an earlier date or move the seating; a person decides which." line is fixed text. It was reproduced as is.
  - "Assessed" includes the cancelled row (13 assessed, of which 1 cancelled), as the procedure and the pasted instructions now say.
- **Limits of this trial.** It was one run, on the invented example only, by one model that had seen the expected tracker. It does not show that the template works on a real office's export, with other date forms, or in other AI products. No dental professional was involved.

## A second, smaller run: two paths the example does not reach

Same product, model and date. The published example has no case that is at the lab, not yet overdue, with its seating already passed, and none overdue with fewer than the check-in days left before its seating. This run used two further invented cases built to reach those two lines. They are not part of the published example. The request, the as-of date and the office settings were the same as the example's (check-in 2 days, look-ahead 7 days, no quarter given), with this file:

**lab-cases-extra.csv**

```
Case,Patient ref,Dentist,Lab,Work type,Sent,Lab due,Seat appointment,Received,Status,Remake of,Remake reason
D-201,P-4102,Dr. K,Lab A,Crown,2026-11-02,2026-11-20,2026-11-13,,at lab,,
D-202,P-4230,Dr. M,Lab B,Crown,2026-11-01,2026-11-12,2026-11-17,,at lab,,
```

**What came out**

```
DENTAL LAB CASE TRACKER, as of Monday, 2026-11-16

Outcome: complete

Coverage: The lab case list "lab-cases-extra.csv" has 2 rows; 2
assessed; 0 could not be assessed. Of those assessed: 2 at the lab; 0
received (0 waiting for the seating, 0 back and past their seating, or
with none booked); 0 cancelled and not tracked. Labs: 2 (Lab A, Lab B).

Inputs: as-of date 2026-11-16, stated in the request; check-in 2 days as
supplied; look-ahead 7 days as supplied; quarter 2026-10-01 to
2026-12-31 by default, counted through 2026-11-16. Dates below are
calculated from the case list; the coordinator confirms each one with
the lab before acting on it.

1. Overdue from the lab: act today
   D-202, P-4230, Dr. M, Lab B, Crown. Sent 2026-11-01; lab due
   2026-11-12, 4 days ago. Seating 2026-11-17; fewer than 2 days remain
   to look it over before then. The coordinator calls the lab today.

2. Due back too late for the seating
   D-201, P-4102, Dr. K, Lab A, Crown. Lab due 2026-11-20; seating
   2026-11-13. The seating date has passed while the case is still at
   the lab. Ask the lab for an earlier date or move the seating; a
   person decides which.

3. At the lab with no seating booked
   None

4. Due back in the next 7 days
   None

5. On track
   None

6. Back from the lab, waiting for the seating
   None

7. Remakes sent this quarter
   None

8. Each lab's record, 2026-10-01 to 2026-11-16
   Rows under "Could not assess" and cancelled rows are not counted.
   Lab A
   - Sent this quarter: 1.
   - Received this quarter: 0; on time 0; late 0 (none).
   - No cases received this quarter.
   - Out now: 1; past the lab's date 0 (none).
   - Remakes of its cases sent this quarter: 0 (none).
   Lab B
   - Sent this quarter: 1.
   - Received this quarter: 0; on time 0; late 0 (none).
   - No cases received this quarter.
   - Out now: 1; past the lab's date 1 (D-202).
   - Remakes of its cases sent this quarter: 0 (none).

9. Check these
   None

10. Could not assess
   None

Nothing was sent, booked or changed. A person contacts every lab and
every patient. The treating dentist writes every prescription, chooses
shade and material, and judges the fit of the work; this tracker records
dates and the office's own words only.
```

**What was observed**

- **D-202** is overdue, and the as-of date (2026-11-16) is after its latest arrival (2026-11-15) and before its seating (2026-11-17), so section 1 used the "fewer than 2 days remain" form, as the rules say. With one day left, the wording reads correctly.
- **D-201** is not overdue (lab due 2026-11-20), but its seating of 2026-11-13 has passed, so it took the "Seating passed" standing and went to section 2 with "The seating date has passed while the case is still at the lab." The rules place it there, but section 2's heading, "Due back too late for the seating", describes it only loosely, and the fixed sentence "Ask the lab for an earlier date or move the seating" fits a seating that has already passed less well than one still ahead: what that patient needs is a new appointment. A person reading the tracker would still see the passed date stated plainly.
- **No cases received.** The procedure writes "no cases received this quarter" in lower case and the format writes "No cases received this quarter." in place of the average line. The format's form was used, as its own bullet.
- **Empty sections and zero counts.** Sections 3 to 7, 9 and 10 read "None", and the Coverage line printed its zero counts. With no extra column, the "Columns not read" sentence was left out, as the format's square brackets allow.
- **Limits.** Two invented rows, one run, by the same model; no stop or decline path was exercised.

## The earlier record this one replaces

An earlier run on the same example, on 10 November 2026 with Claude Sonnet 5.5, was recorded here first. On independent review, its saved output proved identical to the example's tracker, line breaks included, although its notes said the two differed only in line breaks, so it was not known whether that output had been brought into line with the example before it was saved. After that review the template was edited: "Reason not recorded" with a capital R in the procedure; an instruction to work out the weekday of the as-of date; the meaning of "assessed" in the Coverage line; a rewrapped line of the pasted instructions; a full stop after a quoted remake reason in section 7; and "back and past their seating" in place of "its seating" in the Coverage line. Both runs above were made on the template with all of these edits in place, and the example's tracker was updated for the last two.
