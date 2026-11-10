# Dental lab case tracker: an invented example

*Illustrative example with invented data.* An invented two-dentist general dental office on Monday 16 November 2026. The office, the people (Noor, the office coordinator; Bettina, the office manager; the dentists Dr. K and Dr. M), the three labs (Lab A, Lab B and Lab C) and every patient reference are invented. The inputs come first, in full, then the tracker.

## What the coordinator supplied

**The request**

> It's Monday 16 November 2026. Here is the lab case list. Where do our lab cases stand?

**Office settings**

```
Check-in days: 2 (the dentists want a case in the office two days before
the seating)
Look-ahead: 7 days
Coordinator: Noor. Office manager: Bettina. Dentists: Dr. K, Dr. M.
```

No quarter was given, so the tracker uses the calendar quarter that holds the as-of date and says so.

**The lab case list: lab-cases.csv**

The office's export carries a Shade column. The tracker does not read it and does not repeat what it holds.

```
Case,Patient ref,Dentist,Lab,Work type,Sent,Lab due,Seat appointment,Received,Status,Remake of,Remake reason,Shade
C-101,P-2231,Dr. K,Lab A,Crown,2026-09-14,2026-09-28,2026-10-01,2026-09-25,received,,,A2
C-104,P-1187,Dr. M,Lab B,Bridge,2026-10-05,2026-10-19,2026-10-22,2026-10-21,received,,,A3
C-106,P-3012,Dr. K,Lab A,Crown,2026-10-08,2026-10-20,2026-10-23,2026-10-19,received,,,B1
C-109,P-2875,Dr. K,Lab A,Crown,2026-10-15,2026-10-27,2026-10-30,2026-10-27,received,,,A2
C-112,P-1450,Dr. M,Lab C,Night guard,2026-10-20,2026-11-03,2026-11-05,2026-11-04,received,,,
C-115,P-2231,Dr. M,Lab B,Partial denture,2026-10-26,2026-11-13,2026-11-19,,at lab,,,A3
C-117,P-0718,Dr. K,Lab C,Crown,2026-10-27,2026-11-10,2026-11-12,,at lab,,,A1
C-118,P-2875,Dr. K,Lab A,Crown,2026-11-02,2026-11-16,2026-11-20,2026-11-13,received,C-109,Did not fit at the seating appointment; Dr. K asked for a remake,A2
C-120,P-3390,Dr. K,Lab B,Crown,2026-11-04,2026-11-18,2026-11-18,,at lab,,,B2
C-121,P-0954,Dr. M,Lab C,Crown,2026-11-05,2026-11-19,,,at lab,,,A2
C-123,P-2610,Dr. K,Lab A,Veneers,2026-11-09,2026-11-20,2026-11-25,,at lab,,,B1
C-124,P-1187,Dr. M,Lab B,Bridge,2026-11-10,2026-11-24,2026-11-30,,at lab,C-104,,A3
C-125,P-3501,Dr. K,Lab C,Denture,2026-11-11,2026-11-25,2026-12-02,,on hold,,,
C-126,P-2044,Dr. M,Lab A,Crown,2026-11-12,2026-11-26,2026-11-30,,cancelled,,,A2
```

## What came back

*The tracker below is what the template's rules produce from the inputs above, worked through by hand for this page and checked a second time. When the template was tried on these inputs in Claude on 10 November 2026, its output had the same words as this tracker, with two entries broken across lines at different points; the record of that run is published with this example.*

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
   C-125. Status "on hold" is not one of at lab, received or cancelled;
   correct the status in the case list, then run the tracker again.

Nothing was sent, booked or changed. A person contacts every lab and
every patient. The treating dentist writes every prescription, chooses
shade and material, and judges the fit of the work; this tracker records
dates and the office's own words only.
```

## How the figures were reached

- **C-101** was received on 2026-09-25, before the quarter began, and its seating has passed, so it appears only in the Coverage count and not in Lab A's record.
- **C-115:** the seating is 2026-11-19 and the check-in is 2 days, so the case must arrive by 2026-11-17, the day after the as-of date.
- **C-120:** the seating is 2026-11-18, so the case must arrive by 2026-11-16, 2 days before the lab's date of 2026-11-18.
- **C-121** is due back within the look-ahead, but it has no seating booked, so it is listed in section 3 rather than section 4.
- **Lab A's average:** C-106 took 11 days (2026-10-08 to 2026-10-19), C-109 took 12 (2026-10-15 to 2026-10-27) and C-118 took 11 (2026-11-02 to 2026-11-13). The total of 34 days over 3 cases is 11.3. C-109 arrived on its due date, which counts as on time.
- **Lab B:** C-104 took 16 days (2026-10-05 to 2026-10-21) and arrived 2 days after its due date of 2026-10-19. Sent this quarter: C-104, C-115, C-120 and C-124.
- **Lab C:** C-112 took 15 days (2026-10-20 to 2026-11-04) and arrived 1 day after its due date of 2026-11-03. Sent this quarter: C-112, C-117 and C-121; C-125 could not be assessed and is not counted.
- **C-126** is cancelled and is counted only in the Coverage line. "13 assessed" means every row that could be read, so it includes C-126: 6 at the lab, 6 received and 1 cancelled make 13.
- **Remakes:** C-118 replaces C-109 and C-124 replaces C-104, each made by the same lab as the earlier case. The reason for C-118 is copied exactly as the office wrote it; C-124 has none, so the tracker asks for the dentist's reason and supplies none of its own.
