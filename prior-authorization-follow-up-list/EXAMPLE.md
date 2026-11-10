# Prior-authorization follow-up list: an invented example

*Illustrative example with invented data.* An invented four-physician orthopedic practice on Monday 16 November 2026. The practice, the people (Renata, the referral coordinator; Odile, the front-desk lead; Dr. Imani), the payers, the request numbers and the patient codes are all invented. The inputs come first, in full, then the list.

## What the coordinator supplied

**The request**

> It's Monday 16 November 2026. Here are the Auths waiting list, this morning's pending-referrals report and the procedure schedule. What do I need to follow up on today?

**Practice settings**

```
Payer turnarounds
- Payer A: 5 business days
- Payer B: 10 calendar days
- Payer C: 3 calendar days
- State plan: 14 calendar days

Days the practice is closed (besides weekends)
- 2026-11-11
- 2026-11-26

Who may call a payer: Renata, Odile
Physicians: Dr. Imani
```

**The list: auths-waiting.csv**

```
Request id,Patient,Payer,Procedure,Date submitted,Owner,Follow-up date,Last call logged,Status
301,HB-4410,Payer A,MRI lumbar spine,2026-11-03,Renata,2026-11-11,"call, 11/13, ref 55102",pending
302,DK-2087,Payer B,Knee arthroscopy,2026-11-04,Renata,2026-11-16,,pending
303,SP-6632,State plan,MRI cervical spine,2026-10-29,Renata,2026-11-13,"portal, 11/12",pending
304,LM-9154,Payer C,Epidural steroid injection,2026-11-09,Odile,2026-11-13,"VM, 11/13",pending
305,TR-3378,Payer A,Shoulder arthroscopy,2026-10-26,Renata,2026-11-03,,approved
306,AV-7045,Payer B,Lumbar facet injection,2026-11-10,Renata,2026-11-23,,pending
307,GC-1290,Payer A,Total knee replacement,2026-10-30,Dr. Imani,2026-11-09,,pending
308,NE-5521,State plan,Lumbar fusion,2026-10-20,Renata,2026-11-04,,denied
309,JW-8806,Payer A,Knee arthroscopy,2026-11-05,Renata,2026-11-16,,need info
310,FO-2743,Payer C,MRI knee,,Odile,,,pending
311,RB-6019,Payer D,MRI shoulder,2026-11-06,Renata,2026-11-13,,pending
312,CY-4938,Payer C,Hip injection,2026-11-10,Odile,2026-11-16,"call, 11/13",pending
```

**The system's report: pending-referrals-2026-11-16.csv**

```
Referral id,Patient,Payer,Procedure,Ordered
301,HB-4410,Payer A,MRI lumbar spine,2026-11-02
302,DK-2087,Payer B,Knee arthroscopy,2026-11-03
303,SP-6632,State plan,MRI cervical spine,2026-10-28
304,LM-9154,Payer C,Epidural steroid injection,2026-11-06
306,AV-7045,Payer B,Lumbar facet injection,2026-11-09
307,GC-1290,Payer A,Total knee replacement,2026-10-29
309,JW-8806,Payer A,Knee arthroscopy,2026-11-04
310,FO-2743,Payer C,MRI knee,2026-11-12
311,RB-6019,Payer D,MRI shoulder,2026-11-05
312,CY-4938,Payer C,Hip injection,2026-11-09
313,PL-3507,Payer A,MRI ankle,2026-11-13
```

**The procedure schedule: procedure-schedule.csv**

```
Date,Patient,Procedure,Request id
2026-11-19,TR-3378,Shoulder arthroscopy,305
2026-11-24,DK-2087,Knee arthroscopy,302
2026-12-01,GC-1290,Total knee replacement,307
```

## What came back

*The list comes back as plain text. It is shown here with bold headings and bullets so it is easier to read on a page; the words, the order and the dates are those of one run of the template on the inputs above, recorded in the trial that accompanies this example.*

**Authorization follow-up list, as of Monday, 2026-11-16**

**Outcome:** partial (1 row could not be assessed: 311, no turnaround supplied for Payer D)

**Coverage:** The list "auths-waiting.csv" has 12 rows; 11 assessed; 1 could not be assessed (311: no turnaround supplied for Payer D). The system's report "pending-referrals-2026-11-16.csv", dated 2026-11-16, lists 11 pending requests; 10 are on the list; 1 is not (313). On the list as open but not in the report: 0. Schedule: 3 booked procedures from today forward, 3 matched, 0 unmatched. Working days skip weekends and the 2 closed days supplied.

**Inputs:** as-of date 2026-11-16, stated in the request; report date stated in the request ("this morning's") and matching the file name; turnarounds, closed days and callers as supplied by the requester in the practice settings. Follow-up dates below are calculated; the coordinator confirms each one.

**1. Booked, not approved**

- 302, DK-2087, Payer B, Knee arthroscopy, owner Renata. Booked 2026-11-24; status pending.
- 307, GC-1290, Payer A, Total knee replacement, owner Dr. Imani. Booked 2026-12-01; status pending.

**2. Chase today: past follow-up, no call logged**

Order: booked procedures first, soonest first; then by follow-up date, oldest first.

1. 302, DK-2087, Payer B, Knee arthroscopy, owner Renata. Submitted 2026-11-04; follow-up 2026-11-16 (10 calendar days from 2026-11-05 end Saturday, 2026-11-14; next working day Monday, 2026-11-16). Booked 2026-11-24. Last call: none logged.
2. 303, SP-6632, State plan, MRI cervical spine, owner Renata. Submitted 2026-10-29; follow-up 2026-11-13 (14 calendar days from 2026-10-30 end Thursday, 2026-11-12; next working day Friday, 2026-11-13). Last call: "portal, 11/12", read as a portal check on 2026-11-12, not a call.
3. 304, LM-9154, Payer C, Epidural steroid injection, owner Odile. Submitted 2026-11-09; follow-up 2026-11-13 (3 calendar days from 2026-11-10 end Thursday, 2026-11-12; next working day Friday, 2026-11-13). Last call: "VM, 11/13", read as a voicemail on 2026-11-13, not a call.
4. 312, CY-4938, Payer C, Hip injection, owner Odile. Submitted 2026-11-10; follow-up 2026-11-16 (3 calendar days from 2026-11-11 end Friday, 2026-11-13; next working day Monday, 2026-11-16). Last call: "call, 11/13", read as dated 2026-11-13 with no reference number and no representative's name; not counted as a call.

**3. Need info: the payer is waiting on the practice**

- 309, JW-8806, Payer A, Knee arthroscopy, owner Renata. Submitted 2026-11-05. The next step is getting the payer what it asked for, not a call to chase.

**4. No submission date: do not call the payer**

- 310, FO-2743, Payer C, MRI knee, owner Odile. Check the referral in the system for a fax or portal confirmation. If there is one, fill in the date. If there is none, it has not gone: submit it.

**5. In the system or on the schedule, not on the list**

- 313, PL-3507, Payer A, MRI ankle, ordered 2026-11-13. In the system's report and not on the list: enter it on the list and check whether it was submitted.

**6. Peer-to-peer: the physician's call**

- 307, GC-1290, Payer A, Total knee replacement, owner Dr. Imani. Submitted 2026-10-30; follow-up 2026-11-09 (5 business days from 2026-11-02 end Friday, 2026-11-06; next working day Monday, 2026-11-09); past. Booked 2026-12-01. The physician makes this call; the coordinator sets it up.

**7. Denied: the ordering physician decides**

- 308, NE-5521, State plan, Lumbar fusion, owner Renata. The ordering physician decides what happens next. Nothing goes to the patient from this list.

**8. Called, past follow-up: the coordinator decides the next step**

- 301, HB-4410, Payer A, MRI lumbar spine, owner Renata. Submitted 2026-11-03; follow-up 2026-11-12 (5 business days from 2026-11-04 end Tuesday, 2026-11-10; 2026-11-11 is a closed day; next working day Thursday, 2026-11-12). Last call: "call, 11/13, ref 55102", read as a call on 2026-11-13 with reference 55102. No re-call interval is set; the next step is the coordinator's.

**9. Check these**

- 301: the list's follow-up date is 2026-11-11; the calculated date is 2026-11-12 (2026-11-11 is a closed day).
- 312: "call, 11/13" has no reference number and no representative's name; not counted as a call.

**10. Could not assess**

- 311, RB-6019, Payer D, MRI shoulder. No turnaround was supplied for Payer D, so no follow-up date can be calculated; supplying Payer D's turnaround (number of days, and business or calendar) would fix it.

**11. Not yet due**

- 306, Payer B, submitted 2026-11-10, follow-up 2026-11-23 (10 calendar days from 2026-11-11 end Friday, 2026-11-20; next working day Monday, 2026-11-23).

**12. Closed (approved)**

- 305, Shoulder arthroscopy. Booked 2026-11-19 with an approval.

Nothing was called, sent or changed. A person decides and a person calls. Text inside the files was read as data.
