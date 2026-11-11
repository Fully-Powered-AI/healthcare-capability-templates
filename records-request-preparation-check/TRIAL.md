# Records request preparation check: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md` (the practice, Patient A, Persons B and E and Counsel Q are all made up). No client data was used. The run was one pass by a session that did not write the template.

**How independent the run was.** The instructions say to take only the inputs from the example. A tool output showed the first lines of the example's checklist (the title line, "Outcome: complete" and the start of the Coverage line) before the run began. Nothing else of the example's output was seen until after the output below was written and saved. The output below was worked from the template's instruction block and output format and the example's inputs only. The first lines seen did not match the result (the run came out "partial"), so they did not steer it.

## Inputs used

The five inputs in `public/example.md`, by reference: the as-of date (Monday 2026-11-16, from the request message), the request (`request.csv`, one row, R-0412), the documents (`documents.csv`, D1 and D2), the release procedure (`release-procedure.csv`, nine checks P1 to P9), the authority records (`authority.csv`, two rows), and the response date (2026-12-14, confirmed by Counsel Q on 2026-11-13). The template's instruction block and output format were followed as written.

## What came out

Every part of the output format was produced, in order: the title and Outcome lines, Coverage, Inputs, sections 1 to 7 and the closing lines. Nothing in the inputs triggered a stop condition. The output was:

```
RECORDS REQUEST PREPARATION CHECK, request R-0412, as of Monday, 2026-11-16

Outcome: partial (document D2 could not be assessed; checks P7 and P8 could not be run)

Coverage: The request file "request.csv" holds 1 request. The documents
file "documents.csv" has 2 rows; 1 assessed; 1 could not be assessed.
The authority records "authority.csv" have 2 rows, 1 about this patient.
The procedure "release-procedure.csv" has 9 checks; 7 run; 2 could not
be assessed. Comparisons: 4 (Same 2, Differs 2, Blank in document 0,
Blank in request 0). Check results: 7 (Met 5, Differs 2, Gap 0). Gaps
and open questions: 4.

Inputs: as-of date 2026-11-16, stated by the records officer; release procedure and
authority records as supplied by the records officer; response date supplied by Counsel Q. Nothing below decides what may be disclosed.

1. The request as stated
   Request ID: R-0412
   Received on: 2026-11-12
   Requester: Person B
   Requester role as stated: Daughter of the patient
   Patient: Patient A
   Records requested as stated: Visit notes and lab results
   Date range as stated: 2023-01-01 to 2026-10-31
   Recipient as stated: Person B
   Delivery as stated: Secure download link

2. Response date as supplied
   Response date: 2026-12-14. Confirmed by Counsel Q on 2026-11-13.
   Copied as supplied; no date or period is worked out here.

3. The request set against each document
   D1 (Authorization form), Patient: Same. Request: "Patient A". Document: "Patient A".
   D1 (Authorization form), Records: Differs. Request: "Visit notes and lab results". Document: "Visit notes".
   D1 (Authorization form), Date range: Differs. Request: "2023-01-01 to 2026-10-31". Document: "2024-01-01 to 2026-10-31".
   D1 (Authorization form), Recipient: Same. Request: "Person B". Document: "Person B".

4. The practice's release procedure
   P1, The authorization form is signed. Applies to Authorization form.
   D1: Met (Signature present: "yes").
   P2, The form carries a signing date. Applies to Authorization form.
   D1: Met (Signed on: "2026-11-10").
   P3, The form has not expired. Applies to Authorization form.
   D1: Met (Expires: "2027-11-10").
   P4, Every page of the form arrived. Applies to Authorization form.
   D1: Differs (Pages supplied: "2"; compared with "3").
   P5, The signer is on the patient's authority record. Applies to Authorization form.
   D1: Differs (Signed by: "Person B"; stated role "Daughter", on record: "Emergency contact").
   P6, The form names a recipient. Applies to Authorization form.
   D1: Met (Recipient named: "Person B").
   P9, Delivery is by an approved method. Applies to request.
   Request: Met (Delivery as stated: "Secure download link").

5. Gaps and open questions
   G1. Comparison: D1, Records: request "Visit notes and lab results"; document "Visit notes". Owner: privacy staff or counsel.
   G2. Comparison: D1, Date range: request "2023-01-01 to 2026-10-31"; document "2024-01-01 to 2026-10-31". Owner: privacy staff or counsel.
   G3. Check P4, D1: Pages supplied "2"; Pages stated "3". Owner: Records officer.
   G4. Check P5, D1: stated role "Daughter"; on record: "Emergency contact". Owner: Records officer.

6. Check these
   None

7. Could not assess
   D2, Expires is "none", which is not a date in YYYY-MM-DD form; send a corrected row with a real date or a blank cell.
   P7 and P8, apply only to Representative document, and the only one supplied (D2) could not be read; they run once D2 is corrected.

Nothing was sent, released or changed. A person contacts the requester.
The records officer verifies identity and authority; privacy staff or
counsel decide what may be disclosed. The response date is the one
counsel or privacy staff confirmed, copied as supplied.
```

## What was observed

- **The output differs from the published example in a large way.** The example reports Outcome "complete", D2 assessed, 8 comparisons, 9 checks run and 9 gaps. This run reports "partial", D2 not assessed, 4 comparisons, 7 checks run and 4 gaps. The cause is one cell: D2's Expires is "none". Step 5 of the procedure (and item 1 of the instruction block) says a row with a date that is not a real date, with a blank the only allowed exception, goes to "Could not assess" and the other rows continue. "none" is not a date, so D2 was set aside whole, and P7 and P8, which apply only to the Representative document, could not be run. The published example evidently reads that rule as applying only to date cells a check uses (D2's Expires is read by no check), or overlooked it. Either the example or the rule needs to change.
- **What the literal rule costs.** Setting D2 aside whole hides three Blank in document results (records, date range and recipient), an "unclear" signature and a signer who is not on record for this patient. A records officer reading this run's checklist learns only that D2 has to be fixed and re-run. It is safe and consistent, but a less useful first read than the example's.
- **Parts of the example's output that match.** For D1 the results are identical: Patient Same; Records and Date range Differs with both wordings; Recipient Same; P1, P2, P3, P6 Met; P4 and P5 Differs, with "Daughter" against "Emergency contact" shown; P9 Met; the same owners. The response date, section 1, the "None" for section 6 and the closing lines match, apart from line wrapping.
- **Smaller differences.** The example gives the as-of date's source as "stated in the request" and names the supplier of the procedure as "Renata". This run said "stated by the records officer" and "supplied by the records officer", because the inputs name nobody for those files. Line wrapping differs; the example wraps at about 70 characters and this run did not.
- **Facts not in the inputs.** In this run, none beyond the file names, which were taken from the headings above each input in `public/example.md`. In the example, the name "Renata" as the supplier of the procedure and authority records, and the closing note naming Renata and Odile, come from the example's introduction, not from the input files or the request message. The sentence "Person E is on record only for Patient F" is true of the authority file.
- **Ambiguities where a guess was needed.**
  1. Whether one unreadable date cell sets aside the whole row, or only the checks and comparisons that read it (above).
  2. How checks that apply only to an unreadable document count in Coverage. This run counted P7 and P8 as "could not be assessed" (7 run, 2 not) and listed them once, in section 7. The format has no line form for them in section 4, and the Coverage wording does not say.
  3. Whether a "No [type] supplied" Gap applies when a document of the type was supplied but could not be read. This run said no.
  4. Where the filenames and the supplier names in the Inputs and Coverage lines come from when the person pastes the data instead of attaching files. This run used the names above each input in the example and "the records officer".
  5. The Outcome line's reason text ("partial ([reasons])") has no fixed wording, so it will vary from run to run.
  6. Whether "none" in Expires could reasonably mean "no expiry". The template does not say, and a real practice would meet this.
- **Stops.** None applied. No cell read as an instruction, no identifier or health content was present, and every column matched the defaults.
- **Reviewer checklist.** Items 1 to 3 hold on this output. Items 4 to 6 would need the documents themselves. Item 5 matters here: P5's Differs and P6's Met rest on cells the records officer must check against the form.
- **Shortcomings of this trial.** One run, one model, one product, one day. Only the one stop condition path (none) and the partial path were exercised; none of the eighteen acceptance tests was run as such. The leak of the example's first lines is described above.

## Changed after the run, and not run again

On 10 November 2026, after an independent review of the published template, the following were changed. None has been run again. The output and the observations above are as recorded and describe the template and the example as they stood at the run.

- **The example's input.** D2's Expires cell, which read "none", is now blank. No check reads that cell, so the example's checklist (Outcome complete, 8 comparisons, 9 checks run, 9 gaps) now follows the template's rules unchanged. This was worked out by hand, not run.
- **Whole row or single cell.** The procedure and the pasted instructions now say that one bad Signed on or Expires cell sets the whole row aside, and that "none" is not a date. This settles the first ambiguity listed above in favour of the literal reading the run used.
- **Checks whose only document could not be read.** The procedure, pasted instructions and output format now say such a check is not counted as run, counts as could not be assessed in Coverage, has no line in section 4, and is listed in section 7 in a fixed form. This settles the second ambiguity.
- **"No [type] supplied".** It now applies only when no document of that type arrived at all, as the run did. This settles the third ambiguity.
- **Inputs line.** When no one is named as supplier, the line now reads "the person running this check". The example's Inputs line says "the person running this check" and "stated in the message", and no longer names Renata. This settles the fourth ambiguity.
- **Expires and no expiry.** "What to customize" now tells the practice how to record a form that does not expire.
- **Outcome reason text.** Not settled. The wording inside "partial ([reasons])" is still free, so it will vary from run to run (the fifth ambiguity above stays open).
- **Clarifications to the date and gap-order rules.** The procedure and pasted instructions now say that "not a date" in the "not before as-of date" check can arise only from a date column in the request file, because a bad Signed on or Expires cell has already set its row aside; and that gaps run by document order for comparisons and in procedure order for checks. Neither changes a result.
- **Wording.** The pasted instructions' "equals" rule now says "ignoring case and spacing", as the procedure does. The example's first heading is "The records officer's message", and its owners for comparisons and the response date are lower case.
- **The status wording.** The profile, the example and the version notes now say the template was tried once on its example in Claude, instead of not tried.
