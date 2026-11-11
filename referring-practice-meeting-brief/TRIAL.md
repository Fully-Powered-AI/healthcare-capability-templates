# Referring practice meeting brief: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md` (Office K, the practice, the roles, the logs and the figures are all made up). No client data was used.

**Not a blind run, and a second run.** The first run of this date was followed by an independent review, and the instruction block, the output format and the example were then edited slightly (see below). This is the re-run on the revised text, written on the same day. It was not blind: the example file, output included, and the first run's record were both read before the brief was worked out. The brief below was produced by following the revised instruction block and output format on the six inputs, with every count and date worked out again from the inputs, and it was then compared with the published output. Treat the match as a check of the arithmetic and the rules, not as proof that a fresh reader would reach the same brief unaided.

**What changed after the first run.** The instruction block gained the rules for an unreadable date, a missing setting and an area with no owner, a rule that a commitment is matched to a topic by what it is about with the liaison confirming the match, a rule that an approved description mentioning what a withdrawn commitment concerns is listed under "Check these", and "within or on" the answer target. The output format now says the row count of the liaison's note is a count of points. The example's "Prepared" line and "Check these" list changed to match. The first run's brief listed three items under "Check these"; this run lists four.

## Inputs used

The six inputs in `public/example.md`, by reference: the meeting details and settings (Office K, Thursday 10 December 2026, 30 minutes, service owners named for seven areas, threshold 3, target 2 working days, agenda limit 4), the liaison's note of the call (6 points), `commitments.csv` (6 rows), `office-k-questions.csv` (21 rows), `referral-figures.csv` (6 rows) and the three approved service descriptions (D1, D2, D3). The fenced instruction block and the output format were followed as written.

## What came out

Every part of the output format was produced, in order, from the header to the closing line. Nothing in the inputs triggered a stop: no column was missing or renamed, no file held patient detail, and no instruction was written inside a file.

- **Header:** outcome complete; periods September to November 2026 (comparison June to August 2026). Questions log: 21 rows, 15 in the period (14 counted, 1 held), 5 in the comparison period, 1 outside both.
- **What the office raised:** three points kept as written (repeat phone calls about referrals arriving, documents asked for twice, late visit letters). The meeting length and place went to the header. Two points, the knee patients within a week and the one patient's case, were held, and the section says so.
- **Commitments, in the template's order:**
  - C-03, not kept: open, 41 days past due on the meeting date.
  - C-02, reported done on 28 July 2026, no evidence recorded; confirm with the referral intake lead.
  - C-05, open, due 18 December 2026.
  - C-04, kept late: done 14 October, 14 days after the due date.
  - C-01, kept, and raised again (the office's first point, the recurring topic Referral received, and acknowledged within target at 76% against 94%).
  - C-06, withdrawn, no record that the office was told.
  - Summary: 1 not kept, 1 reported done with no evidence, 1 open, 2 kept or kept late, 1 withdrawn.
- **Questions:** 14 counted in the period against 5 in the comparison period; 8 answered within 2 working days, 4 later, 2 not yet answered. Recurring: Referral received 5 (2), Documents requested 4 (1), Visit letter to the referrer 3 (1). Below the threshold: Scheduling and wait 1, Contact route 1 (the row with no topic, placed from its summary).
- **Referral figures:** period received 74, acknowledged within target 56 (76%), returned 13 (18%); comparison received 68, acknowledged 64 (94%), returned 7 (10%).
- **Held for other teams:** the one-week availability question (scheduling supervisor, because no approved description states waiting times), the request to discuss one patient (practice manager), and one clinical question from the log (clinical lead).
- **Agenda, 30 minutes:** opening 5; Visit letter to the referrer 8 (C-03 not kept; no approved wording); Documents requested 6 (C-02; D2); Referral received 6 (C-01, C-05; D1); next steps 5. The 20 minutes left after the opening and next steps divide as 6, 6, 6 with 2 over, so the first subject takes 8. Not on the agenda: none. Each subject ends with one question for the owner to answer before anything is offered.
- **Check these:** C-06 withdrawn with no record the office was told; D1 offers the referral portal while C-06, the portal-account offer, was withdrawn, so D1 needs its approver's confirmation before it is used (the new rule); one question placed by its summary; one question row outside both periods.

## What was observed

**Every required part was produced and the arithmetic held.** The checks in step 13 all came out: each commitment once, each question row once (14 counted, 1 held, 5 comparison, 1 outside), topic counts and answered counts each adding to 14, agenda minutes adding to 30.

**Differences from the published example.** None in a figure, a date, a status, an order, a minute allocation or a "Check these" item. The brief matched in substance. Wording differed in places where the format leaves room, for example how the questions on each subject are phrased. The published example is not wrong on any point I could find.

**Facts in either output that are not in the inputs.** None found. The arithmetic was done again from the inputs: 15 question rows in the period, one held, 14 counted; 5 in the comparison period; one outside both; topic counts 5, 4, 3, 1 and 1; acknowledged 56 of 74 and 64 of 68; 41 and 14 days. Every figure, date and ID in the published output traces to an input.

**Where the template left a choice or a guess:**

1. Which commitments a recurring topic covers is still a judgement, now stated as one: step 8 says to match by what the commitment is about and that the liaison confirms each match. C-05 (a named contact for referral questions) could sit under Referral received or under Contact route; C-04 (the direct line on the contact sheet) could sit under Contact route, which is below the threshold. I put C-05 under Referral received, as the published example does, and C-04 under no recurring topic. The rule does not say which topic wins when two fit, so the confirmation by the liaison carries it.
2. When a commitment is "raised again" by the office's message is also a judgement. C-01 is clear (the figures are worse). C-04 is kept late, a status the rule covers, and it concerns the contact route; the office did not raise that, so I did not mark it, but the rule does not say how close a match must be.
3. The template never checks a kept commitment against the figures except through "raised again", so a kept promise whose measure has since failed is flagged only if it happens to fit that rule.
4. Step 12 says to write "one question" per subject but also says never to write a date. The published questions ask what date an owner "can stand behind". I read that as a question to the owner, not a promise, and it is allowed, but the template could say so.
5. "Answered within or on [target]" is now explicit, and 2 working days counted as within. No gap left here.
6. The "Prepared" line now says the liaison's note is counted in points. I counted 6 points (the heading line is not a point). No gap left here.
7. Approved description D1 says referrals may be sent through the referral portal, while commitment C-06 (offering a portal account) was withdrawn. A rule now asks for both IDs under "Check these", and the brief does so. The rule catches a withdrawn commitment whose subject appears in a description; it does not catch a description that conflicts with an open or kept commitment, and it relies on the reader noticing that the subject is the same. D1 is still named as approved wording to have ready, with the approver to confirm it.
8. The agenda attaches approved descriptions that "bear on" a subject. D2 (send a copy of both sides of the insurance card) bears on a complaint that the card copy is requested twice, but the template does not say whether to point that out. The brief only names the description.
9. Step 11 says to drop the last subject if any would get fewer than 3 minutes, but not what to do when the meeting is shorter than 10 minutes plus 3, so that even one subject does not fit. The ordinary case is covered by acceptance test 10.

**Defects in the template text.** None that stopped the run. The gaps are the judgements listed above, especially numbers 1, 3 and 7.

**Not tested in this run.** The stop conditions (renamed column, patient detail, instruction in a cell), the missing-input paths, the new rules for an unreadable date, a missing setting and an area with no owner, and the declined requests were not exercised, because the invented example triggers none of them. The acceptance tests were not run. This is one run, on one example, by one model.

**Edits after this record (same day).** After the independent review, the template (not the example) was edited in small ways: a tie rule for a commitment that fits two topics (the topic with more questions in the period, then the earlier in the list), a closeness rule for "raised again" (same thing in plain words; when in doubt do not mark it and list it under "Check these"), a clause saying a question to an owner may ask for a date, a rule for a meeting under 13 minutes, the three kept statuses named in the "raised again" rule, and a reworded line about the output format. I did not re-run the brief in full. I re-derived the two points the new rules touch: C-05 fits Referral received (5 questions in the period) and Contact route (1), so it stays under Referral received as in the example; no commitment in the example needed a doubtful "raised again". The brief above is unchanged. Items 1, 2, 4 and 9 under "Where the template left a choice or a guess" describe the text as it stood when this run was made; the new rules address them, and they have not been exercised on a run. Items 3 and 7 remain open and are candidates for a later version.
