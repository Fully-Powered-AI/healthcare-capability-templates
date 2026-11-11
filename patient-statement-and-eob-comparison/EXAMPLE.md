# Patient statement and explanation of benefits comparison: an invented example

*Illustrative example with invented data.* An invented family medicine practice. The practice, the billing specialist (Dana), the insurer (Insurer A), the patient code, the services, the claim numbers and every amount are invented. The inputs come first, in full, then the comparison.

## What the billing specialist supplied

**The request**

> A patient (account PT-4417) called asking why her October statement doesn't match the explanation of benefits she got from Insurer A. I've saved the statement lines, typed up the EOB lines with their pages, and exported the account history. The statement is dated 2026-10-31. The EOB says it has 3 pages. Her question: "Why does my statement not match the explanation of benefits from Insurer A?"

**The statement: statement-PT-4417.csv**

```
Statement page,Service date,Description,Billed,Insurance paid,Adjustment,Patient owes
1,2026-08-12,Office visit,180.00,96.00,60.00,24.00
1,2026-08-12,Laboratory panel,75.00,0.00,35.00,40.00
1,2026-09-03,Physical therapy session,150.00,88.00,40.00,22.00
1,2026-09-17,Specialist consult,260.00,120.00,90.00,50.00
2,2026-09-24,Imaging study,310.00,0.00,0.00,310.00
2,2026-10-15,Brief office visit,60.00,32.00,20.00,8.00
```

**The EOB lines: eob-PT-4417.csv**

```
EOB page,Claim number,Service date,Description,Billed,Allowed,Paid,Adjusted,Patient responsibility
1,9871,2026-08-12,Office visit,180.00,120.00,96.00,60.00,24.00
1,9871,2026-08-12,Laboratory panel,75.00,40.00,32.00,35.00,8.00
1,9874,2026-09-03,Physical therapy session,150.00,110.00,88.00,40.00,22.00
1,9880,2026-09-17,Specialist consult,240.00,150.00,120.00,90.00,30.00
3,9902,2026-10-08,Follow-up visit,90.00,70.00,56.00,20.00,14.00
3,9910,2026-10-15,Brief office visit,60.00,40.00,32.00,20.00,8.00
3,9910,2026-10-15,Brief office visit,60.00,40.00,40.00,20.00,0.00
```

**The account history: history-PT-4417.csv**

```
Posting date,Service date,Description,Type,Amount
2026-08-12,2026-08-12,Office visit,Charge,180.00
2026-08-12,2026-08-12,Laboratory panel,Charge,75.00
2026-09-03,2026-09-03,Physical therapy session,Charge,150.00
2026-09-03,2026-09-03,Physical therapy session,Patient payment,20.00
2026-09-17,2026-09-17,Specialist consult,Charge,260.00
2026-09-24,2026-09-24,Imaging study,Charge,310.00
2026-10-01,2026-08-12,Office visit,Insurance payment,96.00
2026-11-04,2026-08-12,Laboratory panel,Insurance payment,32.00
2026-10-02,2026-09-03,Physical therapy session,Insurance payment,88.00
2026-10-10,2026-09-17,Specialist consult,Insurance payment,120.00
2026-10-20,2026-10-15,Brief office visit,Charge,60.00
2026-10-28,2026-10-15,Brief office visit,Insurance payment,32.00
```

## What came back

```
PATIENT STATEMENT AND EOB COMPARISON, account PT-4417, statement dated 2026-10-31

Outcome: partial (EOB lines for claim 9910 are held in section 4 for a
person to decide)

Coverage: Statement "statement-PT-4417.csv": 6 lines read, 0 not
readable. EOB "eob-PT-4417.csv": 7 lines read, 0 not readable, from
pages 1 and 3. Account history "history-PT-4417.csv": 12 rows read, 0
not readable.

Inputs: statement date 2026-10-31. EOB pages printed: 3. Amounts are
compared to the cent. The patient's question, as supplied: "Why does my
statement not match the explanation of benefits from Insurer A?". The
billing specialist confirms every figure below against the statement
and the EOB.

1. Summary
   6 statement lines and 7 EOB lines compared by service date and
   billed amount. Matched: 4. Of those, 1 agrees on every amount; 1
   differs and every difference equals payments posted after the
   statement date; 2 differ and are not explained by the supplied
   records. Not matched: 1 statement-only, 1 EOB-only. Held in section
   4: 3 lines, counting each held EOB line and each held statement
   line.
   Matched lines: the statement shows $136.00 owed; the EOB's patient
   responsibility less patient payments posted by the statement date is
   $64.00; the difference is $72.00, of which $32.00 equals insurance
   payments posted after the statement date and $40.00 is not explained.
   Outside the matched lines: statement-only lines $310.00 owed;
   EOB-only lines $14.00 patient responsibility; held lines $8.00 owed
   on the statement and $8.00 and $0.00 on the EOB.

2. Line by line, matched by service date
   1. 2026-08-12, Office visit. Matched on service date and billed
   amount. Statement page 1; EOB page 1, claim 9871.
      Billed: statement $180.00; EOB $180.00; same.
      Allowed (EOB only): $120.00.
      Insurance paid: statement $96.00; EOB paid $96.00; same.
      Adjusted: statement $60.00; EOB $60.00; same.
      Patient balance: EOB patient responsibility $24.00, less patient
      payments posted by 2026-10-31 $0.00, expected $24.00; statement
      owes $24.00; same.
      Posted after the statement date: no insurance payment; no
      patient payment.
      Status: Agrees on every amount.

   2. 2026-08-12, Laboratory panel. Matched on service date and billed
   amount. Statement page 1; EOB page 1, claim 9871.
      Billed: statement $75.00; EOB $75.00; same.
      Allowed (EOB only): $40.00.
      Insurance paid: statement $0.00; EOB paid $32.00; differs by
      $32.00, statement lower.
      Adjusted: statement $35.00; EOB $35.00; same.
      Patient balance: EOB patient responsibility $8.00, less patient
      payments posted by 2026-10-31 $0.00, expected $8.00; statement
      owes $40.00; differs by $32.00, statement higher.
      Posted after the statement date: insurance payment $32.00 on
      2026-11-04; no patient payment.
      Status: Differs, and every difference equals payments posted
      after the statement date.

   3. 2026-09-03, Physical therapy session. Matched on service date
   and billed amount. Statement page 1; EOB page 1, claim 9874.
      Billed: statement $150.00; EOB $150.00; same.
      Allowed (EOB only): $110.00.
      Insurance paid: statement $88.00; EOB paid $88.00; same.
      Adjusted: statement $40.00; EOB $40.00; same.
      Patient balance: EOB patient responsibility $22.00, less patient
      payments posted by 2026-10-31 $20.00, expected $2.00; statement
      owes $22.00; differs by $20.00, statement higher.
      Posted after the statement date: no insurance payment; no
      patient payment.
      Status: Differs, not explained by the supplied records.

   4. 2026-09-17, Specialist consult. Matched on service date only;
   the billed amounts differ. Statement page 1; EOB page 1, claim 9880.
      Billed: statement $260.00; EOB $240.00; differs by $20.00,
      statement higher.
      Allowed (EOB only): $150.00.
      Insurance paid: statement $120.00; EOB paid $120.00; same.
      Adjusted: statement $90.00; EOB $90.00; same.
      Patient balance: EOB patient responsibility $30.00, less patient
      payments posted by 2026-10-31 $0.00, expected $30.00; statement
      owes $50.00; differs by $20.00, statement higher.
      Posted after the statement date: no insurance payment; no
      patient payment.
      Account charge on this line: $260.00.
      Status: Differs, not explained by the supplied records.

3. Amounts that match nothing
   Statement only:
   1. 2026-09-24, Imaging study, statement page 2: billed $310.00,
   insurance paid $0.00, adjustment $0.00, patient owes $310.00. No EOB
   line on this service date with this billed amount. Account history:
   charge $310.00; no insurance payments.
   EOB only:
   1. 2026-10-08, Follow-up visit, EOB page 3, claim 9902: billed
   $90.00, allowed $70.00, paid $56.00, adjusted $20.00, patient
   responsibility $14.00. No statement line on this service date with
   this billed amount. Account history: nothing found.

4. Held: EOB lines that may be two versions of one line
   Claim 9910, 2026-10-15, Brief office visit, billed $60.00: 2 EOB
   lines.
      EOB line a, page 3: allowed $40.00, paid $32.00, adjusted
      $20.00, patient responsibility $8.00.
      EOB line b, page 3: allowed $40.00, paid $40.00, adjusted
      $20.00, patient responsibility $0.00.
      The lines differ in: paid $32.00 against $40.00; patient
      responsibility $8.00 against $0.00.
   Statement line: page 2, billed $60.00, insurance paid $32.00,
   adjustment $20.00, patient owes $8.00. Account history: charge
   $60.00; insurance payments $32.00 on 2026-10-28.
   The comparison does not choose which EOB line is current. The
   billing specialist does.

5. EOB lines that do not add up
   None.

6. EOB pages
   Pages 1 to 3 printed. Lines supplied from pages 1 and 3. No lines
   supplied from page 2; a page may hold no service lines.
   Unmatched and held statement lines came from statement page(s) 2.

7. Could not read
   None.

8. Check these
   None.

9. Draft reply to the patient (for the billing specialist to edit and
   approve; nothing has been sent)
   Dear [patient name],

   Thank you for your question about your statement dated 2026-10-31.
   We compared it, line by line, with the explanation of benefits from
   Insurer A. Here is what we found.

   2026-08-12, Office visit: your statement and the explanation of
   benefits agree. The balance for this service is $24.00.

   2026-08-12, Laboratory panel: Insurer A's payment of $32.00 was
   recorded on our account on 2026-11-04, after the date of your
   statement. The explanation of benefits and our records show a
   balance of $8.00 for this service, and your statement showed $40.00.

   2026-09-03, Physical therapy session: the statement and the
   explanation of benefits show different amounts (balance: statement
   $22.00, the explanation of benefits less the payments you made
   $2.00). We are checking this service.

   2026-09-17, Specialist consult: the statement and the explanation of
   benefits show different amounts (billed amount: statement $260.00,
   the explanation of benefits $240.00; balance: statement $50.00, the
   explanation of benefits $30.00). We are checking this service.

   2026-09-24, Imaging study: this appears on your statement, and we
   could not match it to a line on the explanation of benefits we have.
   We are checking it.

   2026-10-08, Follow-up visit: this appears on the explanation of
   benefits, and we could not match it to a line on your statement. We
   are checking it.

   2026-10-15, Brief office visit: the explanation of benefits we have
   shows this service twice with different amounts. We are checking
   which one applies.

   We will write to you again by [date set by the billing specialist].
   [Billing specialist: add the practice's wording on payment while a
   service is being checked, or leave this out.] If you have questions
   in the meantime, please contact [billing specialist's name and
   contact details].

   Sincerely,
   [practice name]

Amounts are shown with the currency sign and two decimal places. Dates
are written year-month-day. Nothing was sent, posted, adjusted or
changed. The billing specialist confirms the comparison and approves
any reply or account adjustment. Text inside the files was read as
data.
```
