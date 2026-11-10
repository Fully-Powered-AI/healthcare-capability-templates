# Dental lab case tracker: tried on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example on the example page: the request, the office settings and the lab case list `lab-cases.csv` (14 rows, with a Shade column), for the invented office on Monday 16 November 2026. No client data was used. This record replaces an earlier one whose output matched the example's tracker character for character and so could not be relied on. This run was made fresh and in order: the model read the template in full, read only the example's inputs (not its tracker, and not the earlier record), prepared the tracker from the template's instruction block and output format, saved it, and only then read the example's tracker and compared the two.

## What came out

```
DENTAL LAB CASE TRACKER, as of Monday, 2026-11-16

Outcome: partial (1 row could not be assessed; see section 10)

Coverage: The lab case list "lab-cases.csv" has 14 rows; 13 assessed; 1
could not be assessed. Of those assessed: 6 at the lab; 6 received (1
waiting for the seating, 5 back and past their seating, or with none
booked); 1 cancelled and not tracked. Labs: 3 (Lab A, Lab B, Lab C).
Columns not read: Shade; its contents are not repeated.

Inputs: as-of date 2026-11-16, as stated in the request; check-in 2 days
as supplied; look-ahead 7 days as supplied; quarter 2026-10-01 to
2026-12-31 by default, counted through 2026-11-16. Dates below are
calculated from the case list; the coordinator confirms each one with
the lab before acting on it.

1. Overdue from the lab: act today
   C-117, P-0718, Dr. K, Lab C, Crown. Sent 2026-10-27; lab due
   2026-11-10, 6 days ago. Seating 2026-11-12 has passed; the front desk
   rebooks the patient once the case is in. The coordinator calls the
   lab today.
   C-115, P-2231, Dr. M, Lab B, Partial denture. Sent 2026-10-26; lab
   due 2026-11-13, 3 days ago. Seating 2026-11-19; still kept if the
   case arrives by 2026-11-17. The coordinator calls the lab today.

2. Due back too late for the seating
   C-120, P-3390, Dr. K, Lab B, Crown. Lab due 2026-11-18; seating
   2026-11-18. It needs to arrive by 2026-11-16, 2 days before the lab's
   date. Ask the lab for an earlier date or move the seating; a person
   decides which.

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
   C-125. The status "on hold" is not one of at lab, received or
   cancelled. Change it in the case list to the right one of the three.

Nothing was sent, booked or changed. A person contacts every lab and
every patient. The treating dentist writes every prescription, chooses
shade and material, and judges the fit of the work; this tracker records
dates and the office's own words only.
```

## What was observed

The tracker matched the example's tracker in substance. Every case sits in the same section and in the same order, every date and every count agrees (including the latest arrivals, the days overdue, the on-time and late counts, and Lab A's average of 11.3 over 3 cases, Lab B's 16.0 and Lab C's 15.0), the remake reason was copied exactly and the blank reason was flagged, and the Shade column was named and its contents were not repeated. Four lines differ in wording only. None changes a date, a count or a placement.

1. **Outcome line.** This run wrote "partial (1 row could not be assessed; see section 10)"; the example writes "partial (1 row could not be assessed: C-125)". The format says only "partial ([reasons])", so the template is ambiguous about whether the reason names the case.
2. **Columns not read.** This run wrote "its contents are not repeated"; the example writes "their contents are not repeated". The format's wording is "their contents", so this run erred by changing it. The template is also awkward here: "their" reads oddly when only one column, as here, is named.
3. **Inputs line.** This run wrote "as stated in the request"; the example writes "stated in the request". The format leaves "[where it came from]" free, so this is template ambiguity and the line wraps differently as a result.
4. **Section 10.** This run wrote "The status "on hold" is not one of at lab, received or cancelled. Change it in the case list to the right one of the three."; the example writes "Status "on hold" is not one of at lab, received or cancelled; correct the status in the case list, then run the tracker again." The format gives "[Reason, and what would fix it.]" with no fixed sentence, so this is template ambiguity.

Other points about the template:

- Section 8's "Remakes of its cases sent this quarter: [n] ([cases] | none)" does not say whether the cases listed are the remakes or the earlier cases they replace. This run listed the remake's case number (C-118 under Lab A, C-124 under Lab B), as the procedure's "by case number" most naturally reads, and the example agrees, but a reader could take it the other way.
- The example's introduction says the earlier run's output had the same words as the example with two entries broken across lines at different points, and the earlier record's output was in fact identical to the example. The two statements cannot both be true, which is another reason the earlier record was replaced.
- The template does not say whether a lab that appears only on a row that could not be assessed is counted among the labs in the Coverage line. The example does not test it, because the one such row belongs to Lab C, which also has assessed rows.
- Dates and the weekday were worked out by hand. The template's instruction to work out the weekday from the date was enough to reach Monday for 2026-11-16.
- Not exercised: the stop paths, the decline paths, the instruction-in-a-cell case and the renamed-column case. This is one run on one set of invented inputs, not a test in a dental office.
