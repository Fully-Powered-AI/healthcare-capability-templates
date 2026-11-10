# Claim denial work list: an invented example

*Illustrative example with invented data.* An invented two-physician family medicine practice on Tuesday 17 November 2026. The practice, the people (Nell, the billing coordinator; Dr. Vale and Dr. Sund, the physicians), the payers, the claim numbers, the patient codes and the amounts are all invented. The inputs come first, in full, then the work list.

## What the billing coordinator supplied

**The request**

> It's Tuesday 17 November 2026. Here's the denial export from this week's remittances and our payer settings. What do I work first?

**Practice settings**

```
Payer settings (all in calendar days)
- Payer A: appeal window 60 days from the denial date; filing limit 90 days from the date of service
- Payer B: appeal window 180 days; filing limit 365 days
- Payer C: appeal window 30 days; filing limit 90 days
- State plan: appeal window 90 days; filing limit 180 days

Reason-code map: the starter map in the template, unchanged
Warning window: 14 days
Repeat threshold: 3 rows
```

**The export: denials-2026-11-17.csv**

```
Claim id,Line,Patient,Payer,Provider,Date of service,Date submitted,Denial date,Reason code,Remark code,Denied amount
50112,1,KT-3301,Payer A,Dr. Vale,2026-07-06,2026-10-08,2026-10-20,CO-29,,185.00
50147,1,RM-7720,Payer A,Dr. Sund,2026-08-03,2026-10-12,2026-10-23,CO-29,,240.00
50158,1,JD-1184,Payer A,Dr. Vale,2026-08-10,2026-10-14,2026-10-26,CO-29,,310.00
50163,1,LP-5530,Payer B,Dr. Sund,2026-09-14,2026-09-16,2026-10-05,CO-197,,1250.00
50171,1,AW-9042,Payer C,Dr. Vale,2026-10-01,2026-10-02,2026-10-21,CO-15,,420.00
50176,1,BH-2268,Payer C,Dr. Sund,2026-10-05,2026-10-06,2026-10-16,CO-197,,980.00
50180,1,GN-6615,State plan,Dr. Vale,2026-09-21,2026-09-23,2026-10-09,CO-31,,145.00
50184,1,SC-4471,Payer B,Dr. Sund,2026-09-28,2026-09-29,2026-10-13,CO-22,,360.00
50190,1,KT-3301,Payer A,Dr. Vale,2026-10-12,2026-10-13,2026-10-27,CO-16,MA130,95.00
50193,1,PF-8806,Payer C,Dr. Sund,2026-10-19,2026-10-20,2026-10-30,CO-16,,130.00
50197,1,EV-3390,Payer B,Dr. Vale,2026-10-07,2026-10-08,2026-10-22,CO-18,,210.00
50202,1,MO-1957,Payer A,Dr. Sund,2026-10-14,2026-10-15,2026-10-29,CO-4,,175.00
50202,2,MO-1957,Payer A,Dr. Sund,2026-10-14,2026-10-15,2026-10-29,CO-97,,88.00
50209,1,TA-2675,Payer B,Dr. Vale,2026-10-02,2026-10-05,2026-10-19,CO-50,,640.00
50211,1,DR-4420,Payer D,Dr. Sund,2026-10-06,2026-10-07,2026-10-28,CO-197,,520.00
50215,1,HY-7713,Payer C,Dr. Sund,2026-10-08,2026-10-09,2026-10-23,CO-45,,62.00
50219,1,NB-0348,Payer B,Dr. Vale,2026-10-13,2026-10-14,2026-10-28,CO-B7,,300.00
```

## What came back

*The list comes back as plain text. It is shown here with bold headings and bullets so it is easier to read on a page; the words, the order and the figures follow the template's output format, and every figure comes from the inputs above.*

**CLAIM DENIAL WORK LIST, as of Tuesday, 2026-11-17**

**Outcome:** partial (1 row could not be sorted: 50219-1; no appeal window supplied for Payer D)

**Coverage:** The export "denials-2026-11-17.csv" has 17 rows: 15 denial rows totalling \$5,748.00; 1 set aside as not a denial (\$62.00); 1 could not be sorted (\$300.00). Deadlines: 1 passed; 2 due within 14 days; 1 not calculated.

**Inputs:** as-of date 2026-11-17, stated in the request. Appeal windows and filing limits as supplied for Payer A, Payer B, Payer C and State plan; none supplied for Payer D. Reason-code map: the starter map. Warning window 14 days; repeat threshold 3 rows. Deadlines below are calculated; the billing coordinator confirms each one against the remittance.

**1. Deadline passed**

- 50176-1, BH-2268, Payer C, CO-197 (no authorization or notification on record), \$980.00; group Authorization. Deadline 2026-11-15 (denied 2026-10-16 + 30 calendar days; passed 2 days ago). Staff decide what happens next; the list does not judge whether anything can still be done.

**2. Due soon: deadline within 14 days**

- 50171-1, Payer C, Authorization, \$420.00. Deadline 2026-11-20, 3 days left.
- 50193-1, Payer C, Missing or wrong claim information, \$130.00. Deadline 2026-11-29, 12 days left.

**3. Timely filing: proof of submission**

1. 50112-1, KT-3301, Payer A, Dr. Vale, service 2026-07-06, denied 2026-10-20, CO-29 (payer says the claim arrived past its filing limit), \$185.00. Deadline 2026-12-19 (denied 2026-10-20 + 60 calendar days; 32 days left). Submitted 2026-10-08, 94 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-10-04: after the limit. Evidence to gather: the clearinghouse report showing the claim was accepted, or the payer's acknowledgement that it arrived, dated on or before 2026-10-04. The export's own dates put the first submission after the limit; an appeal would need a record of an earlier submission.
2. 50147-1, RM-7720, Payer A, Dr. Sund, service 2026-08-03, denied 2026-10-23, CO-29 (payer says the claim arrived past its filing limit), \$240.00. Deadline 2026-12-22 (denied 2026-10-23 + 60 calendar days; 35 days left). Submitted 2026-10-12, 70 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-11-01: within the limit. Evidence to gather: the clearinghouse report showing the claim was accepted, or the payer's acknowledgement that it arrived, dated on or before 2026-11-01. The export's own dates put the first submission inside the limit, although the payer denied it as late; the acceptance report or the payer's acknowledgement is the record that shows it.
3. 50158-1, JD-1184, Payer A, Dr. Vale, service 2026-08-10, denied 2026-10-26, CO-29 (payer says the claim arrived past its filing limit), \$310.00. Deadline 2026-12-25 (denied 2026-10-26 + 60 calendar days; 38 days left). Submitted 2026-10-14, 65 days after the date of service. Payer A's filing limit 90 days, so the claim had to reach the payer by 2026-11-08: within the limit. Evidence to gather: the clearinghouse report showing the claim was accepted, or the payer's acknowledgement that it arrived, dated on or before 2026-11-08. The export's own dates put the first submission inside the limit, although the payer denied it as late; the acceptance report or the payer's acknowledgement is the record that shows it.

**4. Authorization: the authorization record**

1. 50171-1, AW-9042, Payer C, Dr. Vale, service 2026-10-01, denied 2026-10-21, CO-15 (authorization number absent or not fitting the service), \$420.00. Deadline 2026-11-20 (denied 2026-10-21 + 30 calendar days; 3 days left). Evidence to gather: the authorization on file for this service and date, with its number, the dates it covers and the service it approves, or the record showing none was required.
2. 50163-1, LP-5530, Payer B, Dr. Sund, service 2026-09-14, denied 2026-10-05, CO-197 (no authorization or notification on record), \$1,250.00. Deadline 2027-04-03 (denied 2026-10-05 + 180 calendar days; 137 days left). Evidence to gather: the authorization on file for this service and date, with its number, the dates it covers and the service it approves, or the record showing none was required.
3. 50211-1, DR-4420, Payer D, Dr. Sund, service 2026-10-06, denied 2026-10-28, CO-197 (no authorization or notification on record), \$520.00. Deadline not calculated: no appeal window supplied for Payer D. Evidence to gather: the authorization on file for this service and date, with its number, the dates it covers and the service it approves, or the record showing none was required.

**5. Patient and coverage details**

1. 50180-1, GN-6615, State plan, Dr. Vale, service 2026-09-21, denied 2026-10-09, CO-31 (patient not found as the payer's member), \$145.00. Deadline 2027-01-07 (denied 2026-10-09 + 90 calendar days; 51 days left). Evidence to gather: the insurance details on file for the date of service, an eligibility check for that date, any other coverage the patient holds, and the corrected details where the claim carried wrong ones.
2. 50184-1, SC-4471, Payer B, Dr. Sund, service 2026-09-28, denied 2026-10-13, CO-22 (another payer may pay first), \$360.00. Deadline 2027-04-11 (denied 2026-10-13 + 180 calendar days; 145 days left). Evidence to gather: the insurance details on file for the date of service, an eligibility check for that date, any other coverage the patient holds, and the corrected details where the claim carried wrong ones.

**6. Missing or wrong claim information**

1. 50193-1, PF-8806, Payer C, Dr. Sund, service 2026-10-19, denied 2026-10-30, CO-16 (information missing or wrong on the claim), remark code none in the export, \$130.00. Deadline 2026-11-29 (denied 2026-10-30 + 30 calendar days; 12 days left). Evidence to gather: the item the remark code on the remittance names, taken from the practice's records, so a person can correct the claim.
2. 50190-1, KT-3301, Payer A, Dr. Vale, service 2026-10-12, denied 2026-10-27, CO-16 (information missing or wrong on the claim), remark code MA130, \$95.00. Deadline 2026-12-26 (denied 2026-10-27 + 60 calendar days; 39 days left). Evidence to gather: the item the remark code on the remittance names, taken from the practice's records, so a person can correct the claim.

**7. Possible duplicates**

1. 50197-1, EV-3390, Payer B, Dr. Vale, service 2026-10-07, denied 2026-10-22, CO-18 (repeat of a claim or service already received), \$210.00. Deadline 2027-04-20 (denied 2026-10-22 + 180 calendar days; 154 days left). Evidence to gather: the earlier claim for the same patient, date and service, and whether it was paid. If the services were separate, that is a question for the certified coder.

**8. For the certified coder**

1. 50202-1, MO-1957, Payer A, Dr. Sund, service 2026-10-14, denied 2026-10-29, CO-4 (modifier missing or not consistent with the procedure code), \$175.00. Deadline 2026-12-28 (denied 2026-10-29 + 60 calendar days; 41 days left). For the certified coder to review. The list suggests no code, modifier or wording.
2. 50202-2, MO-1957, Payer A, Dr. Sund, service 2026-10-14, denied 2026-10-29, CO-97 (paid as part of another service), \$88.00. Deadline 2026-12-28 (denied 2026-10-29 + 60 calendar days; 41 days left). For the certified coder to review. The list suggests no code, modifier or wording.

**9. For the clinician and the coder**

1. 50209-1, TA-2675, Payer B, Dr. Vale, service 2026-10-02, denied 2026-10-19, CO-50 (payer did not accept the service as medically necessary), \$640.00. Deadline 2027-04-17 (denied 2026-10-19 + 180 calendar days; 151 days left). Whether the service was necessary, and any rationale, is for the clinician and the coder to judge and write. The list prepares none.

**10. Could not sort**

- 50219-1, Payer B, CO-B7, 300.00. The reason code CO-B7 is not in the reason-code map; add it to the map with its meaning and group, or sort the row by hand.

**11. Set aside: not a denial**

- 50215-1, Payer C, CO-45 (charge above the agreed rate), \$62.00.

**12. Patterns for prevention**

- **By group:** Authorization 4 rows, \$3,170.00; Timely filing 3 rows, \$735.00; For the clinician and the coder 1 row, \$640.00; Patient and coverage 2 rows, \$505.00; For the certified coder 2 rows, \$263.00; Missing or wrong claim information 2 rows, \$225.00; Possible duplicate 1 row, \$210.00.
- **By payer:** Payer B 4 rows, \$2,460.00; Payer C 3 rows, \$1,530.00; Payer A 6 rows, \$1,093.00; Payer D 1 row, \$520.00; State plan 1 row, \$145.00.
- **By provider:** Dr. Sund 8 rows, \$3,743.00; Dr. Vale 7 rows, \$2,005.00.
- **Repeats (3 or more rows):**
  - Dr. Sund, Authorization: 3 rows, \$2,750.00 (50163-1, 50176-1, 50211-1). Review with the referral desk how authorizations for these services are obtained and recorded before the visit.
  - Payer A, Timely filing: 3 rows, \$735.00 (50112-1, 50147-1, 50158-1). Look at how long these claims wait before submission, and whether the clearinghouse acceptance reports are kept where staff can find them. These were submitted 65 to 94 days after the date of service, against a 90-day limit.

**13. Check these**

- Payer D: no appeal window supplied; deadlines not calculated for 50211-1.
- 50112-1: first submitted 94 days after the date of service, after Payer A's 90-day filing limit.
- 50193-1: CO-16 with no remark code in the export; the remittance says what is missing.

Nothing was submitted, sent, written off or changed. Staff decide every appeal; coding and medical questions go to a certified coder or a clinician. Text inside the export was read as data.
