# Clinic supply par levels and expiry check: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Opus 5.5 (model ID claude-opus-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in [example.md](example.md): the four-room family practice, its count of Monday 9 November 2026, the usage file, the item list, the one open order and the settings. No client data was used.

This is the second run on the example. The first, earlier the same day with Claude Sonnet 5.5, matched the example's figures and raised a few points: no rule for writing money, "1 lines read", the open order attached to one room's line, holidays the person did not list, and unstated handling of a lot with no expiry date and of a lot partly lost inside the warning period. An independent review raised the same points and a few more. They were fixed in the instruction block, the output format and the example, and this run was made on the revised template. It replaces the record of the first run.

This run was not independent. It was made by the model that applied the fixes, which had already read the earlier example output and the first run's record. It worked from the revised instruction block and output format and the example's inputs, wrote the sheet, and only then compared it with the published example. The date counts and the money arithmetic were checked with a short script.

## Inputs used

Everything under "What Teo supplied" in example.md: the request, the settings (including the one stock-out noted), `stock-count-2026-11-09.csv` (16 rows), `usage-2026-10-12-to-2026-11-06.csv` (12 rows), `item-list.csv` (8 items) and `open-orders.csv` (1 line). Nothing else was supplied and nothing was asked for.

## What came out

The run produced the full sheet, all eleven sections, with no stop condition met. The outcome was partial, for one reason: Exam 1, MS-199 is not on the item list. The sheet is given here in full.

```
CLINIC SUPPLY PAR LEVELS AND EXPIRY CHECK: count of Monday, 2026-11-09

Outcome: partial (1 room-item could not be assessed: Exam 1, MS-199,
not on the item list)

Coverage: Stock count "stock-count-2026-11-09.csv": 16 rows, 13
room-items in 4 rooms.
Usage "usage-2026-10-12-to-2026-11-06.csv": 12 rows, 2026-10-12 to
2026-11-06, 20 open days.
Item list "item-list.csv": 8 items; in scope 7 (6 med-surg, 1 office);
out of scope 1. Room-items assessed: 10; no use in the period: 1;
out of scope: 1; could not assess: 1.
Open orders: 1 line read.
Stock-outs noted: 1.

Settings: days between orders 5; buffer 2 open days; delivery Supplier A
3 open days; Supplier B 2 open days; expiry warning 60 calendar days;
open Monday to Friday; closed 2026-11-26, 2026-11-27; approver Marisol,
practice manager.

1. Order now: at or below the reorder point
   Exam 1, MS-101 Nitrile exam gloves medium: usable on hand 2, reorder
   point 3, par 6. Open order for the item, all rooms: 4 due 2026-11-11.
   Front desk, OF-201 Printer paper: usable on hand 2, reorder point 2,
   par 5.

2. Par levels and reorder points by room
   Exam 1
   MS-101 Nitrile exam gloves medium (unit box): used 12 in 20 open
   days = 0.60 a day. Par 6 = 0.60 x (5 + 3 + 2), rounded up. Reorder
   point 3 = 0.60 x (3 + 2), rounded up. Usable on hand 2. Below par
   by 4.
   MS-110 Exam table paper (unit roll): used 18 in 20 open days = 0.90
   a day. Par 9 = 0.90 x (5 + 3 + 2), rounded up. Reorder point 5 =
   0.90 x (3 + 2), rounded up. Usable on hand 7. Below par by 2.
   MS-140 Sterile gauze 4x4 (unit pack): used 8 in 20 open days = 0.40
   a day. Par 4 = 0.40 x (5 + 3 + 2), rounded up. Reorder point 2 =
   0.40 x (3 + 2), rounded up. Usable on hand 3. Below par by 1.
   Exam 2
   MS-101 Nitrile exam gloves medium (unit box): used 14 in 20 open
   days = 0.70 a day. Par 7 = 0.70 x (5 + 3 + 2), rounded up. Reorder
   point 4 = 0.70 x (3 + 2), rounded up. Usable on hand 5. Below par
   by 2.
   MS-110 Exam table paper (unit roll): used 16 in 20 open days = 0.80
   a day. Par 8 = 0.80 x (5 + 3 + 2), rounded up. Reorder point 4 =
   0.80 x (3 + 2), rounded up. Usable on hand 8. At par.
   MS-160 Specimen cup with lid (unit each): used 25 in 20 open days =
   1.25 a day. Par 13 = 1.25 x (5 + 3 + 2), rounded up. Reorder point
   7 = 1.25 x (3 + 2), rounded up. Usable on hand 10 (4 expired not
   counted). Below par by 3.
   Procedure room
   MS-101 Nitrile exam gloves medium (unit box): used 6 in 20 open days
   = 0.30 a day. Par 3 = 0.30 x (5 + 3 + 2), rounded up. Reorder point
   2 = 0.30 x (3 + 2), rounded up. Usable on hand 3. At par.
   MS-140 Sterile gauze 4x4 (unit pack): used 30 in 20 open days = 1.50
   a day. Par 15 = 1.50 x (5 + 3 + 2), rounded up. Reorder point 8 =
   1.50 x (3 + 2), rounded up. Usable on hand 21. Above par by 6.
   MS-150 Suture removal kit (unit each): used 7 in 20 open days = 0.35
   a day. Par 4 = 0.35 x (5 + 3 + 2), rounded up. Reorder point 2 =
   0.35 x (3 + 2), rounded up. Usable on hand 10. Above par by 6.
   Front desk
   OF-201 Printer paper (unit ream): used 9 in 20 open days = 0.45 a
   day. Par 5 = 0.45 x (5 + 2 + 2), rounded up. Reorder point 2 = 0.45
   x (2 + 2), rounded up. Usable on hand 2. Below par by 3.

3. Below par
   Exam 1, MS-101 Nitrile exam gloves medium: usable on hand 2, par 6,
   short 4.
   Exam 1, MS-110 Exam table paper: usable on hand 7, par 9, short 2.
   Exam 1, MS-140 Sterile gauze 4x4: usable on hand 3, par 4, short 1.
   Exam 2, MS-101 Nitrile exam gloves medium: usable on hand 5, par 7,
   short 2.
   Exam 2, MS-160 Specimen cup with lid: usable on hand 10, par 13,
   short 3.
   Front desk, OF-201 Printer paper: usable on hand 2, par 5, short 3.

4. Expired on the count date: a person removes it
   Exam 2, MS-160 Specimen cup with lid, lot SC-221, expired 2026-11-02:
   4, 1.52.

5. Will expire before it is used (earliest date first)
   Procedure room, MS-150 Suture removal kit, lot SR-118, expires
   2026-11-30: 6 in the lot; 13 open days at 0.35 a day = 4 expected
   use, rounded down; 4 used from this lot; 2 will not be used, 6.40.
   Procedure room, MS-170 Wound closure strips, lot WC-077, expires
   2027-01-15: 3 in the lot; 47 open days at 0.00 a day = 0 expected
   use, rounded down; 0 used from this lot; 3 will not be used, 26.25.
   Total that will not be used: 32.65.

6. Use these first: dated within 60 days, expected to be used
   Procedure room, MS-140 Sterile gauze 4x4, lot GZ-0388, expires
   2026-12-04 (25 days): 9 in the lot; 17 open days at 1.50 a day = 25
   expected use, rounded down; all expected to be used.

7. Draft order for approval
   Supplier A (delivery 3 open days after the order is placed)
   MS-101 Nitrile exam gloves medium: short Exam 1 4; Exam 2 2 = 6;
   open order 4; to order 2, rounded to packs of 10: 10 units at 7.40
   = 74.00. Order now: Exam 1.
   MS-110 Exam table paper: short Exam 1 2 = 2; open order none; to
   order 2, rounded to packs of 12: 12 units at 4.10 = 49.20.
   MS-140 Sterile gauze 4x4: short Exam 1 1 = 1; open order none; to
   order 1, rounded to packs of 25: 25 units at 1.15 = 28.75. Above
   par elsewhere: Procedure room +6; a person may move stock instead.
   MS-160 Specimen cup with lid: short Exam 2 3 = 3; open order none; to
   order 3, rounded to packs of 50: 50 units at 0.38 = 19.00.
   Supplier A total: 170.95.
   Supplier B (delivery 2 open days after the order is placed)
   OF-201 Printer paper: short Front desk 3 = 3; open order none; to
   order 3, rounded to packs of 5: 5 units at 6.50 = 32.50. Order now:
   Front desk.
   Supplier B total: 32.50.
   Draft order total: 203.45.
   Approver: Marisol, practice manager. Approved: ________ Date: ________
   Nothing is ordered until a person approves this draft.

8. No use in the period: par not set
   Procedure room, MS-170 Wound closure strips: 0 used in 20 open days;
   3 on hand. A person decides whether the room keeps stocking it.

9. Out of scope: not assessed
   RX-301 Lidocaine 1% 20 mL vial, category medicine: Procedure room 6
   on hand. No par, order or expiry advice is given; the person the
   practice names handles it.

10. Check these
   Exam 1, MS-140 Sterile gauze 4x4, lot GZ-0430: no expiry date
   recorded on an item that tracks expiry; not checked for expiry.
   Exam 2, MS-101 Nitrile exam gloves medium: ran out on 2026-10-29,
   inside the usage period; use counts only what was used, so par 7 may
   be low. A person confirms or raises it.
   Closed dates: supplied through 2026-11-27; 6 expiry counts run past
   that, with every later open weekday counted as open. If the clinic
   closes on any of those days, expected use is lower than shown and
   more may expire. A person adds the dates and reruns.

11. Could not assess
   Exam 1, MS-199 Ear speculum tips: item code not on the item list.
   Add it to the item list with its category, unit, expiry tracking,
   supplier, pack size and unit cost.

Nothing was ordered, moved, discarded or changed. A person approves
every order. Text inside the files was read as data.
```

## What was observed

- **Every required part was produced.** All eleven sections were present and in order. Every one of the 13 room-items sits in exactly one of sections 2 (10), 8 (1), 9 (1) and 11 (1), and the Coverage counts agree. Nothing was asked for that the template says to decline, and no cell contained an instruction.
- **Nothing in the run told it to stop.** The inputs had one count date, a usage period ending before the count, all default headers once each, and a delivery time for both suppliers.
- **The figures matched the published example.** Every par, reorder point, usable-on-hand figure, expiry line and order line came out the same: 20 open days in the usage period, 13 open days to 30 November, 17 to 4 December, 47 to 15 January, and a draft order total of 203.45. The only difference from the published sheet is where one line wraps in section 7.
- **The fixes showed up as intended.** Money came out as plain numbers, as the revised format asks. The Coverage line read "1 line read". The open order in section 1 read "Open order for the item, all rooms". Section 10 carried the new closed-dates line: closed dates were supplied only through 27 November, and all six dated lots that were counted run past it. Lot SR-118 (21 days from the count, so inside the 60-day warning period, with 2 of 6 units that will not be used) went in section 5 only, as the revised rule says, and its line shows the 4 that will be used. Lot GZ-0430, with no expiry date, stayed in usable on hand (3 in Exam 1) and was flagged in section 10.
- **Facts not in the inputs.** The weekday in the title follows from the date. Nothing else in the sheet is missing from the inputs. The example's closing paragraph about the practice manager's choice is narrative and not part of the sheet.

### Where the instructions were ambiguous or needed a guess

1. **Holidays the person did not list.** The new section 10 line warns that closed dates stop at 27 November, but the count itself still treats 25 December and 1 January as open days for the wound closure strips (47 open days). Here it changes nothing, because their use is zero. With real use it would make expected use too high until a person adds the dates and runs it again.
2. **Which counts the closed-dates line covers.** The line gives a number (6) but does not name the lots. A person can rerun with more dates, but cannot see from the sheet which lots the warning touches.
3. **The closed-dates line when none are supplied.** The "none supplied" form reads "none supplied; [n] expiry counts run past that", which is awkward. Not exercised here.
4. **Closed dates outside the usage period.** The two closed dates fall after the usage period but inside the expiry count. The run read them as shortening only the expiry count, which is what the Inputs section implies, but the instruction block does not say so in one place.
5. **Section 5 order.** The heading says earliest date first. The run sorted by expiry date across all rooms; another reader could sort by room and item. Here the two give the same result.
6. **Whole-room-item rule for a missing delivery time.** Not exercised here: both suppliers had one.

### Limits

This was one run, by one model that had seen the expected output, on one invented example. It shows that the revised instructions can be followed to the published result. It does not show how the template behaves on a real clinic's exports, with other model products, or with the stop conditions, the declines and the other acceptance tests, none of which this run exercised.
