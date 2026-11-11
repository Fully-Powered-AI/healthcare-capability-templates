# Patient statement and explanation of benefits comparison: a trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md` (the request, the statement file, the EOB file and the account history file). No client data was used. The model that ran the template did not write it, and it read the example's output only after producing its own.

## What came out

The model followed the instruction block and the output format in `member/template.md` on those inputs. This is the output it produced, in full.

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
   4: 3 lines.
   Matched lines: the statement shows $136.00 owed; the EOB's patient
   responsibility less patient payments posted by the statement date is
   $64.00; the difference is $72.00, of which $32.00 equals payments
   posted after the statement date and $40.00 is not explained.
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
   explanation of benefits less the payments you made $30.00). We are
   checking this service.

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
are written year-month-day. [Service date, claim] pairs are shown as
written in the files. Nothing was sent, posted, adjusted or changed.
The billing specialist confirms the comparison and approves any reply
or account adjustment. Text inside the files was read as data.
```

## What was observed

- **Every required part was produced.** All nine sections, the title, Outcome, Coverage and Inputs lines, and the closing paragraph. Nothing in the inputs made the run stop: the headers matched, no names or other identifying details appeared, no row was unreadable, and the statement date was given.
- **The result.** Four lines matched (one agrees, one is explained by an insurance payment posted after the statement date, two are not explained), one statement line and one EOB line matched nothing, and the two EOB lines for claim 9910 were held with their statement line. The summary totals came to $136.00 owed on the statement against $64.00 expected, a difference of $72.00, of which $32.00 is explained and $40.00 is not.
- **Differences from the published example.** (This describes the example as it stood before the edits listed at the end of this record; most of these differences were removed by those edits.) The numbers, statuses, counts, line order and section 3, 4 and 6 content are the same. The differences were small:
  - The Outcome reason is worded differently ("held in section 4 for a person to decide" against "held for a person to decide").
  - The published example's reply says the explanation of benefits is the one "that you gave us". The inputs do not say the patient gave the practice the explanation of benefits (the request says only that she "got" it), so this run left those words out. That is a fact in the published output that is not in the inputs.
  - The statement-only line's account history reads "no insurance payments" here and "no insurance payment found" in the example.
  - The example's closing paragraph leaves out the sentence the template's format carries about [service date, claim] pairs being shown as written; this run kept it.
- **Facts not in the inputs.** None in this run's output other than what the template's fixed wording supplies. The practice name, the patient's name, the date for a further reply, the payment wording and the specialist's contact details were left as placeholders, as instructed.
- **Told to stop for.** Nothing. No instruction in any cell, no code or necessity question, no request to send or adjust.
- **Where the instructions were ambiguous and a guess was needed.**
  - "Held in section 4: [n] lines" does not say whether the statement line counts. This run counted three (two EOB lines and the statement line), as the published example does.
  - The summary's split of the difference into "equals payments posted after the statement date" and "not explained" is not defined for lines whose status is "not explained". Here only one line had postings after the statement date, so any reading gives $32.00 and $40.00; with more lines it would not be clear.
  - The wording "[that you gave us]" has no stated condition for when it applies.
  - The reply sentence "the explanation of benefits less the payments you made" is fixed wording, so it is used even where the patient made no payment (the specialist consult), where it reads oddly.
  - The Outcome reason has no fixed wording.
  - For the statement-only line the history form ("insurance payments [x] on [date] | nothing found") has no wording for "a charge but no payments"; this run wrote "charge $310.00; no insurance payments".
  - The sentence about "[service date, claim] pairs" in the closing paragraph has no clear meaning, since the output never rewrites those values.
  - The held statement line's own status (it matched the date and billed amount of the held lines) is left to the specialist, which is as intended, but the template does not say so in the procedure.
- **Shortcomings.** This was one run, by one model, on one invented example, in one product. It shows the template can be followed to the output it describes. It does not show how it performs on real files, with a different product, or in a medical practice, and none of that has been tried. The template's acceptance tests were not run; only the example's inputs were.

## Edits made after this run

The template, the example and the profile were revised on 10 November 2026, after this run and after an independent pre-review (not the later review that approved the template). These edits have not been run again, and no recorded output or observation above was changed. Several change what a run prints, as noted.

- The rule for the status "every difference equals payments posted after the statement date" no longer counts patient payments: Patient owes minus the expected balance must equal the insurance payments posted after the statement date alone, because a patient payment posted after the statement date is in neither figure. The reply sentence for that status no longer offers "and your payment of [amount]" as part of the explanation; a separate sentence reports a patient payment posted after the statement date, and nothing more. Two acceptance tests were added for it. This run had no payment of that kind, so its statuses stand.
- The words "that you gave us" now have a condition: only when the request says the patient supplied the explanation of benefits. The example's request does not, so the example no longer carries them, as in this run. The profile no longer says the patient supplied the explanation of benefits.
- The profile and the version notes now say the template was tried once on its example, in the form used for the claim denial work list.
- The split of the summary's difference is defined: the explained part is the sum of (Patient owes minus the expected balance) over the lines with the explained status, and the rest is not explained. This run's figures ($32.00 and $40.00) are the same under the definition.
- The held count in section 1 is defined as each held EOB line plus each held statement line. This run counted three, as the definition does.
- The sentence about [service date, claim] pairs was deleted from the closing paragraph. This run kept it; a run on the revised template would not print it, and the example does not.
- A fixed form was added for an account history with a charge and no payments ("charge [x]; no insurance payments"), as this run wrote it. The example now matches it, and says "insurance payments" in the held block as this run did.
- The Outcome reasons have fixed wording: "EOB lines for claim [number] are held in section 4 for a person to decide". This run's wording is the same, and the example now matches it.
- When patient payments posted by the statement date are $0.00, or no account history was supplied, the reply says "the explanation of benefits" for the balance, not "less the payments you made". This run used the longer phrase for the specialist consult (balance: $0.00 paid); a run on the revised template would not, and the example no longer does.
- The procedure now says the statement line held with duplicate EOB lines gets no status, and the instruction block says the history match ignores case and spacing and that a pair matched on date alone uses the statement's description. The line about the columns now says once that every column in every file needs a value.
- The credits now say that no third-party package contributed. A later wording change, not run again, drops that sentence and says only that it was written by Fully Powered AI from its own published map of the work, with no third-party text.
- A later review added: the example now prints the full held-count wording and says "insurance payments" in the summary, the Outcome line is wrapped, a sign on Adjusted is ignored in the EOB arithmetic check, and the instructions say plainly that history rows of other types, or matching no line, go to section 8. None changes what a run decides; none has been run again.
