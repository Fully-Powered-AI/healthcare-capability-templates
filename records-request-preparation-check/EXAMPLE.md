# Records request preparation check: an invented example

*Illustrative example with invented data.* An invented family-medicine practice, on Monday 16 November 2026. The practice, the people (Renata, the records officer; Odile, who leads privacy; Counsel Q, who confirmed the response date) and the patient and requesters (Patient A, Person B, Person E, Patient F) are all invented. The inputs come first, in full, then the checklist.

## What the records officer supplied

**The records officer's message**

> It's Monday 2026-11-16. A request for copies came in on Thursday. Here is the request, the two documents that came with it, our release procedure, our authority records and the response date Counsel Q confirmed. What is missing?

**Response date, as supplied by Counsel Q:** 2026-12-14, confirmed by Counsel Q on 2026-11-13.

**The request: request.csv**

```
Request ID,Received on,Requester,Requester role as stated,Patient,Records requested as stated,Date range as stated,Recipient as stated,Delivery as stated
R-0412,2026-11-12,Person B,Daughter of the patient,Patient A,Visit notes and lab results,2023-01-01 to 2026-10-31,Person B,Secure download link
```

**The documents: documents.csv**

```
Document ID,Document type,Signed by,Signer role as stated,Signed on,Patient named,Records named,Date range named,Recipient named,Expires,Signature present,Pages supplied,Pages stated
D1,Authorization form,Person B,Daughter,2026-11-10,Patient A,Visit notes,2024-01-01 to 2026-10-31,Person B,2027-11-10,yes,2,3
D2,Representative document,Person E,Representative,2026-11-11,Patient A,,,,,unclear,1,1
```

**The practice's release procedure: release-procedure.csv**

```
Check ID,Requirement,Applies to,Field,Test,Owner
P1,The authorization form is signed,Authorization form,Signature present,equals: yes,Records officer
P2,The form carries a signing date,Authorization form,Signed on,filled,Records officer
P3,The form has not expired,Authorization form,Expires,not before as-of date,Records officer
P4,Every page of the form arrived,Authorization form,Pages supplied,matches: Pages stated,Records officer
P5,The signer is on the patient's authority record,Authorization form,Signed by,listed in authority records,Records officer
P6,The form names a recipient,Authorization form,Recipient named,filled,Records officer
P7,A representative document is signed,Representative document,Signature present,equals: yes,Records officer
P8,The representative is on the patient's authority record,Representative document,Signed by,listed in authority records,Records officer
P9,Delivery is by an approved method,request,Delivery as stated,equals: Secure download link | Postal mail,Records officer
```

**The authority records: authority.csv**

```
Patient,Person,Role on record,Recorded on
Patient A,Person B,Emergency contact,2024-06-02
Patient F,Person E,Parent,2025-01-20
```

## What came back

*The checklist below is what the template's rules produce from the inputs above, worked through by hand for this page. The template was tried once on an earlier form of these inputs in Claude on 10 November 2026. That run found that D2's Expires cell, which then read "none", is not a date, so the rules set the whole row aside; the cell is now blank, and the changed example and instructions have not been run again. The record is in the trial.*

```
RECORDS REQUEST PREPARATION CHECK, request R-0412, as of Monday, 2026-11-16

Outcome: complete

Coverage: The request file "request.csv" holds 1 request. The documents
file "documents.csv" has 2 rows; 2 assessed; 0 could not be assessed.
The authority records "authority.csv" have 2 rows, 1 about this patient.
The procedure "release-procedure.csv" has 9 checks; 9 run; 0 could not
be assessed. Comparisons: 8 (Same 3, Differs 2, Blank in document 3,
Blank in request 0). Check results: 9 (Met 5, Differs 2, Gap 2). Gaps
and open questions: 9.

Inputs: as-of date 2026-11-16, stated in the message; release procedure
and authority records as supplied by the person running this check;
response date as supplied by Counsel Q. Nothing below decides what may be disclosed.

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
   D1 (Authorization form), Patient: Same. Request: "Patient A".
   Document: "Patient A".
   D1 (Authorization form), Records: Differs. Request: "Visit notes and
   lab results". Document: "Visit notes".
   D1 (Authorization form), Date range: Differs. Request: "2023-01-01 to
   2026-10-31". Document: "2024-01-01 to 2026-10-31".
   D1 (Authorization form), Recipient: Same. Request: "Person B".
   Document: "Person B".
   D2 (Representative document), Patient: Same. Request: "Patient A".
   Document: "Patient A".
   D2 (Representative document), Records: Blank in document. Request:
   "Visit notes and lab results". Document: "(blank)".
   D2 (Representative document), Date range: Blank in document. Request:
   "2023-01-01 to 2026-10-31". Document: "(blank)".
   D2 (Representative document), Recipient: Blank in document. Request:
   "Person B". Document: "(blank)".

4. The practice's release procedure
   P1, The authorization form is signed. Applies to Authorization form.
   D1: Met (Signature present: "yes").
   P2, The form carries a signing date. Applies to Authorization form.
   D1: Met (Signed on: "2026-11-10").
   P3, The form has not expired. Applies to Authorization form.
   D1: Met (Expires: "2027-11-10").
   P4, Every page of the form arrived. Applies to Authorization form.
   D1: Differs (Pages supplied: "2"; compared with "3").
   P5, The signer is on the patient's authority record. Applies to
   Authorization form.
   D1: Differs (Signed by: "Person B"; stated role "Daughter", on
   record: "Emergency contact").
   P6, The form names a recipient. Applies to Authorization form.
   D1: Met (Recipient named: "Person B").
   P7, A representative document is signed. Applies to Representative
   document.
   D2: Gap (Signature present: "unclear").
   P8, The representative is on the patient's authority record. Applies
   to Representative document.
   D2: Gap (Signed by: "Person E"; not on record for this patient).
   P9, Delivery is by an approved method. Applies to request.
   Request: Met (Delivery as stated: "Secure download link").

5. Gaps and open questions
   G1. Comparison: D1, Records: the request says "Visit notes and lab
   results"; the document says "Visit notes". Owner: privacy staff or
   counsel.
   G2. Comparison: D1, Date range: the request says "2023-01-01 to
   2026-10-31"; the document says "2024-01-01 to 2026-10-31". Owner:
   privacy staff or counsel.
   G3. Comparison: D2, Records: the document is blank; the request says
   "Visit notes and lab results". Owner: privacy staff or counsel.
   G4. Comparison: D2, Date range: the document is blank; the request
   says "2023-01-01 to 2026-10-31". Owner: privacy staff or counsel.
   G5. Comparison: D2, Recipient: the document is blank; the request
   says "Person B". Owner: privacy staff or counsel.
   G6. Check P4, D1: Pages supplied "2"; compared with "3". Owner:
   Records officer.
   G7. Check P5, D1: Person B is on record for Patient A as "Emergency
   contact"; the stated role is "Daughter". Owner: Records officer.
   G8. Check P7, D2: Signature present reads "unclear". Owner: Records
   officer.
   G9. Check P8, D2: Person E is not on record for Patient A. Owner:
   Records officer.

6. Check these
   None

7. Could not assess
   None

Nothing was sent, released or changed. A person contacts the requester.
The records officer verifies identity and authority; privacy staff or
counsel decide what may be disclosed. The response date is the one
counsel or privacy staff confirmed, copied as supplied.
```

A note on what the checklist leaves alone: it does not say whether the first document is enough, whether the second is genuine, or what the practice may send. Person E is on record only for Patient F, and the checklist treats that as no record for Patient A. Those calls belong to the records officer and to privacy staff or counsel.
