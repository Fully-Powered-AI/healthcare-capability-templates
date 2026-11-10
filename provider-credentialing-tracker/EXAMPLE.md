# Provider credentialing and re-credentialing tracker: an invented example

*Illustrative example with invented data.* An invented family-medicine practice with four clinicians, on Monday 16 November 2026. The practice, the people (Marisol, the credentialing coordinator; Teodor, the practice manager; the clinicians Dr. A, Dr. B, NP C, PA D and Dr. E), the boards, the insurer and the payers are all invented. The inputs come first, in full, then the tracker.

## What the coordinator supplied

**The request**

> It's Monday 16 November 2026. Here are the roster, the credential items and our requirements. Where do we stand?

**Practice settings**

```
Clinician types and the items each requires
- Physician: State licence; Controlled-substance registration; Board
  certification; Malpractice insurance; Exclusion-list check; Payer
  enrolment: Payer A; Payer enrolment: Payer B
- Nurse practitioner: State licence; Controlled-substance registration;
  Professional certification; Malpractice insurance; Exclusion-list check;
  Payer enrolment: Payer A; Payer enrolment: Payer B
- Physician assistant: State licence; Professional certification;
  Malpractice insurance; Exclusion-list check; Payer enrolment: Payer A;
  Payer enrolment: Payer B

Items: how each falls due; lead time; accepted verification source
- State licence: on expiry; 90 days; State board website
- Controlled-substance registration: on expiry; 60 days; Registration lookup
- Board certification: on expiry; 90 days; Specialty board lookup
- Professional certification: on expiry; 90 days; Certifying body lookup
- Malpractice insurance: on expiry; 45 days; Insurer certificate
- Exclusion-list check: every 30 days from Verified on; 0 days; Exclusion
  list search
- Payer enrolment: Payer A: on expiry (the payer's re-credentialing date);
  120 days; Payer portal
- Payer enrolment: Payer B: on expiry (the payer's re-credentialing date);
  120 days; Payer portal

Look-ahead: 30 days
Coordinator: Marisol. Practice manager: Teodor. Medical director: Dr. A.
```

**The roster: roster.csv**

```
Clinician,Type,Status,Start date
Dr. A,Physician,active,2019-03-04
Dr. B,Physician,active,2022-08-15
NP C,Nurse practitioner,active,2024-01-08
PA D,Physician assistant,joining,2026-12-07
```

**The credential items: credential-items.csv**

```
Clinician,Item,Issued by,Verification source,Verified on,Verified by,Expires,Document on file,Status
Dr. A,State licence,State medical board,State board website,2025-02-03,Marisol,2027-01-31,yes,current
Dr. A,Controlled-substance registration,Registration authority,Registration lookup,2024-09-10,Marisol,2027-09-30,yes,current
Dr. A,Board certification,Specialty board,Specialty board lookup,2025-01-15,Marisol,2028-12-31,yes,current
Dr. A,Malpractice insurance,Insurer A,Insurer certificate,2026-01-05,Marisol,2026-12-31,yes,renewal applied
Dr. A,Exclusion-list check,Exclusion list,Exclusion list search,2026-10-20,Marisol,none,yes,current
Dr. A,Payer enrolment: Payer A,Payer A,Payer portal,2024-05-20,Marisol,2027-05-20,yes,current
Dr. A,Payer enrolment: Payer B,Payer B,Payer portal,2025-02-10,Marisol,2028-02-10,yes,current
Dr. B,State licence,State medical board,Copy from clinician,2026-06-01,Marisol,2028-06-30,yes,current
Dr. B,Controlled-substance registration,Registration authority,Registration lookup,2026-03-02,Marisol,2026-12-31,yes,current
Dr. B,Board certification,Specialty board,Specialty board lookup,2025-09-08,Marisol,2026-11-10,yes,current
Dr. B,Malpractice insurance,Insurer A,Insurer certificate,2026-01-05,Marisol,2026-12-31,yes,renewal applied
Dr. B,Exclusion-list check,Exclusion list,Exclusion list search,2026-10-20,Marisol,none,yes,current
Dr. B,Payer enrolment: Payer A,Payer A,Payer portal,2023-03-15,Marisol,2027-03-01,yes,current
NP C,State licence,State nursing board,State board website,2025-04-07,Marisol,2027-04-30,yes,current
NP C,Controlled-substance registration,Registration authority,Registration lookup,2024-02-12,Marisol,2027-02-10,yes,current
NP C,Professional certification,Certifying body,Certifying body lookup,2025-11-03,Marisol,2030-12-31,no,current
NP C,Malpractice insurance,Insurer A,Insurer certificate,2026-01-05,Marisol,2026-12-31,yes,renewal applied
NP C,Exclusion-list check,Exclusion list,Exclusion list search,2026-10-09,Marisol,none,yes,current
NP C,Payer enrolment: Payer A,Payer A,Payer portal,2024-03-01,Marisol,2027-03-01,yes,current
NP C,Payer enrolment: Payer B,Payer B,Payer portal,2024-06-01,Marisol,2027-06-01,yes,current
PA D,State licence,State medical board,State board website,2026-11-02,Marisol,2028-09-30,yes,current
PA D,Professional certification,Certifying body,Certifying body lookup,2026-11-02,Marisol,2028-12-31,yes,current
PA D,Controlled-substance registration,Registration authority,Registration lookup,2026-11-02,Marisol,2029-10-31,yes,current
PA D,Malpractice insurance,Insurer A,,,,,no,applied
PA D,Exclusion-list check,Exclusion list,Exclusion list search,2026-11-02,Marisol,none,yes,current
PA D,Payer enrolment: Payer A,Payer A,,,,,no,applied
PA D,Payer enrolment: Payer B,Payer B,,,,,no,not started
Dr. E,State licence,State medical board,State board website,2024-07-01,Marisol,2026-12-31,yes,current
```

## What came back

*The tracker below is what the template's rules produce from the inputs above, worked through by hand for this page. When the template was tried once on these inputs in Claude on 10 November 2026, its output agreed with this tracker on every standing, date, count and section and differed only in wording; the record of that run is published with this example. The words "(not the accepted source)" on Dr. B's State licence in section 9 were added to the output format after that run.*

```
CREDENTIALING TRACKER, as of Monday, 2026-11-16

Outcome: partial (1 row could not be assessed: Dr. E, not on the roster)

Coverage: The roster "roster.csv" lists 4 clinicians (3 active, 1
joining); 0 could not be assessed (none). The items file
"credential-items.csv" has 28 rows; 27 assessed; 1 could not be
assessed. Required items: 27 across the clinicians assessed; 26 have a
row; 1 has no row (Dr. B: Payer enrolment: Payer B). Rows for items the
clinician's type does not require: 1 (PA D: Controlled-substance
registration).

Inputs: as-of date 2026-11-16, stated in the request; requirements, lead
times and accepted sources as supplied by Marisol in the practice
settings; look-ahead 30 days as supplied. Due and start dates below are
calculated; the coordinator confirms each one before acting on it.

Files: 1 of 4 complete.

1. Lapsed or overdue: act today
   NP C, Exclusion-list check, Exclusion list. Due 2026-11-08, 8 days ago.
   Status current. Check whether it was renewed or re-checked and not
   recorded; if not, the coordinator raises it with the practice manager
   today.
   Dr. B, Board certification, Specialty board. Due 2026-11-10, 6 days
   ago. Status current. Check whether it was renewed or re-checked and
   not recorded; if not, the coordinator raises it with the practice
   manager today.

2. Start now: the start date has been reached
   Dr. B, Controlled-substance registration, Registration authority. Due
   2026-12-31; start 2026-11-01. 45 days left.
   Dr. A, State licence, State medical board. Due 2027-01-31; start
   2026-11-02. 76 days left.
   Dr. B, Payer enrolment: Payer A, Payer A. Due 2027-03-01; start
   2026-11-01. 105 days left.
   NP C, Payer enrolment: Payer A, Payer A. Due 2027-03-01; start
   2026-11-01. 105 days left.

3. Starts in the next 30 days
   Dr. A, Exclusion-list check, Exclusion list. Start 2026-11-19; due
   2026-11-19.
   Dr. B, Exclusion-list check, Exclusion list. Start 2026-11-19; due
   2026-11-19.
   PA D, Exclusion-list check, Exclusion list. Start 2026-12-02; due
   2026-12-02.
   NP C, Controlled-substance registration, Registration authority. Start
   2026-12-12; due 2027-02-10.

4. Waiting on the issuer
   Dr. A, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   Dr. B, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   NP C, Malpractice insurance, Insurer A. Renewal applied; the current
   item is valid through 2026-12-31.
   PA D, Malpractice insurance, Insurer A. Applied: first application, not
   yet granted.
   PA D, Payer enrolment: Payer A, Payer A. Applied: first application,
   not yet granted.

5. Files not yet complete
   PA D (Physician assistant, joining, starts Monday, 2026-12-07, in 21
   days):
   - Malpractice insurance: applied.
   - Payer enrolment: Payer A: applied.
   - Payer enrolment: Payer B: missing (status "not started").
   Dr. B (Physician):
   - State licence: not verified at the accepted source.
   - Board certification: lapsed 2026-11-10.
   - Payer enrolment: Payer B: missing (no row).
   NP C (Nurse practitioner):
   - Professional certification: document not on file.
   - Exclusion-list check: lapsed 2026-11-08.

6. Complete files
   Dr. A (Physician)

7. Check these
   Dr. B, State licence: verified at "Copy from clinician"; the accepted
   source is "State board website".
   PA D, Controlled-substance registration: not required for Physician
   assistant; dated below, not counted toward the file.

8. Could not assess
   Dr. E, State licence. Dr. E is not on the roster; add Dr. E to the
   roster or remove the row.

9. Tracker by clinician
   Dr. A (Physician, active). File: complete.
   - State licence: issued by State medical board. Verified 2025-02-03 by
     Marisol at State board website. Due 2027-01-31 (expiry); start
     2026-11-02. Document on file: yes. Standing: Start now.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2024-09-10 by Marisol at Registration lookup. Due 2027-09-30
     (expiry); start 2027-08-01. Document on file: yes. Standing: Current.
   - Board certification: issued by Specialty board. Verified 2025-01-15
     by Marisol at Specialty board lookup. Due 2028-12-31 (expiry); start
     2028-10-02. Document on file: yes. Standing: Current.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-20
     by Marisol at Exclusion list search. Due 2026-11-19 (next check, 30
     days from 2026-10-20); start 2026-11-19. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2024-05-20 by
     Marisol at Payer portal. Due 2027-05-20 (expiry); start 2027-01-20.
     Document on file: yes. Standing: Current.
   - Payer enrolment: Payer B: issued by Payer B. Verified 2025-02-10 by
     Marisol at Payer portal. Due 2028-02-10 (expiry); start 2027-10-13.
     Document on file: yes. Standing: Current.

   Dr. B (Physician, active). File: not complete.
   - State licence: issued by State medical board. Verified 2026-06-01 by
     Marisol at Copy from clinician (not the accepted source). Due
     2028-06-30 (expiry); start 2028-04-01. Document on file: yes.
     Standing: Current.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2026-03-02 by Marisol at Registration lookup. Due 2026-12-31
     (expiry); start 2026-11-01. Document on file: yes. Standing: Start
     now.
   - Board certification: issued by Specialty board. Verified 2025-09-08
     by Marisol at Specialty board lookup. Due 2026-11-10 (expiry); start
     2026-08-12. Document on file: yes. Standing: Lapsed.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-20
     by Marisol at Exclusion list search. Due 2026-11-19 (next check, 30
     days from 2026-10-20); start 2026-11-19. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2023-03-15 by
     Marisol at Payer portal. Due 2027-03-01 (expiry); start 2026-11-01.
     Document on file: yes. Standing: Start now.
   - Payer enrolment: Payer B: Missing (no row).

   NP C (Nurse practitioner, active). File: not complete.
   - State licence: issued by State nursing board. Verified 2025-04-07 by
     Marisol at State board website. Due 2027-04-30 (expiry); start
     2027-01-30. Document on file: yes. Standing: Current.
   - Controlled-substance registration: issued by Registration authority.
     Verified 2024-02-12 by Marisol at Registration lookup. Due 2027-02-10
     (expiry); start 2026-12-12. Document on file: yes. Standing: Starts
     soon.
   - Professional certification: issued by Certifying body. Verified
     2025-11-03 by Marisol at Certifying body lookup. Due 2030-12-31
     (expiry); start 2030-10-02. Document on file: no. Standing: Current.
   - Malpractice insurance: issued by Insurer A. Verified 2026-01-05 by
     Marisol at Insurer certificate. Due 2026-12-31 (expiry); start
     2026-11-16. Document on file: yes. Standing: Renewal applied.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-10-09
     by Marisol at Exclusion list search. Due 2026-11-08 (next check, 30
     days from 2026-10-09); start 2026-11-08. Document on file: yes.
     Standing: Lapsed.
   - Payer enrolment: Payer A: issued by Payer A. Verified 2024-03-01 by
     Marisol at Payer portal. Due 2027-03-01 (expiry); start 2026-11-01.
     Document on file: yes. Standing: Start now.
   - Payer enrolment: Payer B: issued by Payer B. Verified 2024-06-01 by
     Marisol at Payer portal. Due 2027-06-01 (expiry); start 2027-02-01.
     Document on file: yes. Standing: Current.

   PA D (Physician assistant, joining, starts 2026-12-07). File: not
   complete.
   - State licence: issued by State medical board. Verified 2026-11-02 by
     Marisol at State board website. Due 2028-09-30 (expiry); start
     2028-07-02. Document on file: yes. Standing: Current.
   - Professional certification: issued by Certifying body. Verified
     2026-11-02 by Marisol at Certifying body lookup. Due 2028-12-31
     (expiry); start 2028-10-02. Document on file: yes. Standing: Current.
   - Malpractice insurance: Applied with Insurer A; not dated.
   - Exclusion-list check: issued by Exclusion list. Verified 2026-11-02
     by Marisol at Exclusion list search. Due 2026-12-02 (next check, 30
     days from 2026-11-02); start 2026-12-02. Document on file: yes.
     Standing: Starts soon.
   - Payer enrolment: Payer A: Applied with Payer A; not dated.
   - Payer enrolment: Payer B: Missing (status "not started").
   - Controlled-substance registration: issued by Registration authority.
     Verified 2026-11-02 by Marisol at Registration lookup. Due 2029-10-31
     (expiry); start 2029-09-01. Document on file: yes. Standing: Current.

Nothing was sent, submitted or changed. A person contacts every board,
insurer and payer. Privileges, peer review and any judgement of a
clinician's competence stay with the practice's medical leadership.
```
