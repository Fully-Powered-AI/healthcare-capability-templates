# Clinic supply par levels and expiry check: an invented example

*Illustrative example with invented data.* An invented four-room family practice after its stock count on Monday 9 November 2026. The practice, the people (Teo, the medical assistant who orders supplies; Marisol, the practice manager), Supplier A, Supplier B, the item codes, the lot numbers, the quantities and the prices are all invented. The inputs come first, in full, then the sheet.

## What Teo supplied

**The request**

> Here are Monday's count, the last four weeks' usage, our item list and the one open order. Settings below. Please prepare the par levels, the expiry check and a draft order for Marisol.

**Settings**

```
Usage period: 2026-10-12 to 2026-11-06
Open: Monday to Friday
Closed: 2026-11-26, 2026-11-27
Days between orders: 5 open days (we order once a week)
Delivery: Supplier A 3 open days; Supplier B 2 open days
Buffer: 2 open days
Expiry warning: 60 calendar days
Approver: Marisol, practice manager
Stock-outs noted: Exam 2 ran out of MS-101 on 2026-10-29
```

**The stock count: stock-count-2026-11-09.csv**

```
Count date,Room,Item code,Item,Lot,Expiry date,On hand
2026-11-09,Exam 1,MS-101,Nitrile exam gloves medium,,,2
2026-11-09,Exam 1,MS-110,Exam table paper,,,7
2026-11-09,Exam 1,MS-140,Sterile gauze 4x4,GZ-0430,,3
2026-11-09,Exam 1,MS-199,Ear speculum tips,,,2
2026-11-09,Exam 2,MS-101,Nitrile exam gloves medium,,,5
2026-11-09,Exam 2,MS-110,Exam table paper,,,8
2026-11-09,Exam 2,MS-160,Specimen cup with lid,SC-221,2026-11-02,4
2026-11-09,Exam 2,MS-160,Specimen cup with lid,SC-305,2027-06-30,10
2026-11-09,Procedure room,MS-101,Nitrile exam gloves medium,,,3
2026-11-09,Procedure room,MS-140,Sterile gauze 4x4,GZ-0388,2026-12-04,9
2026-11-09,Procedure room,MS-140,Sterile gauze 4x4,GZ-0412,2027-09-30,12
2026-11-09,Procedure room,MS-150,Suture removal kit,SR-118,2026-11-30,6
2026-11-09,Procedure room,MS-150,Suture removal kit,SR-140,2027-04-30,4
2026-11-09,Procedure room,MS-170,Wound closure strips,WC-077,2027-01-15,3
2026-11-09,Procedure room,RX-301,Lidocaine 1% 20 mL vial,L5521,2027-02-28,6
2026-11-09,Front desk,OF-201,Printer paper,,,2
```

**The usage: usage-2026-10-12-to-2026-11-06.csv**

```
Room,Item code,Units used
Exam 1,MS-101,12
Exam 1,MS-110,18
Exam 1,MS-140,8
Exam 2,MS-101,14
Exam 2,MS-110,16
Exam 2,MS-160,25
Procedure room,MS-101,6
Procedure room,MS-140,30
Procedure room,MS-150,7
Procedure room,MS-170,0
Procedure room,RX-301,4
Front desk,OF-201,9
```

**The item list: item-list.csv**

```
Item code,Item,Category,Unit,Tracks expiry,Supplier,Pack size,Unit cost
MS-101,Nitrile exam gloves medium,med-surg,box,no,Supplier A,10,7.40
MS-110,Exam table paper,med-surg,roll,no,Supplier A,12,4.10
MS-140,Sterile gauze 4x4,med-surg,pack,yes,Supplier A,25,1.15
MS-150,Suture removal kit,med-surg,each,yes,Supplier A,10,3.20
MS-160,Specimen cup with lid,med-surg,each,yes,Supplier A,50,0.38
MS-170,Wound closure strips,med-surg,box,yes,Supplier A,6,8.75
OF-201,Printer paper,office,ream,no,Supplier B,5,6.50
RX-301,Lidocaine 1% 20 mL vial,medicine,vial,yes,Supplier A,10,2.90
```

**The open orders: open-orders.csv**

```
Item code,Supplier,Units,Expected date
MS-101,Supplier A,4,2026-11-11
```

## What came back

*Every figure below follows from the inputs above. The usage period has 20 open days (four weeks, Monday to Friday, no closed day in it). Counting from Tuesday 10 November, the open days skip weekends and the two closed days, 26 and 27 November. Money is written as plain numbers, in the currency of the item list's unit costs.*

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
   order 3, rounded to packs of 5: 5 units at 6.50 = 32.50. Order
   now: Front desk.
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

Marisol reads the draft order, decides whether to move six packs of gauze from the procedure room instead of buying 25, and approves, changes or holds each supplier's lines before Teo places anything.
