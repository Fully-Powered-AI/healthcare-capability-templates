# Appointment confirmation and no-show follow-up: tried on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

This run used only the invented inputs from the worked example (`public/example.md`): the physiotherapy practice called Practice A, its settings, its five pieces of approved wording, the two exports, the open-slots list and the morning's reply notes. No client data was used. The assistant that ran it did not write the template. It followed the instruction block and the output format in `member/template.md`, and it did not read the example's output until its own list was finished.

## What came out

This is the whole list, as plain text in the template's format.

```
APPOINTMENT CONFIRMATIONS AND NO-SHOW FOLLOW-UP, prepared Thursday 19 November 2026

Outcome: complete

Coverage: Confirmation-day export "appointments-2026-11-20.csv": 9 rows for Friday 20 November 2026; 6 to contact; 1 already confirmed; 1 not to be contacted; 1 cancelled; 0 could not be used. Today's export "appointments-2026-11-19.csv": 6 rows; 3 no-shows. Open slots "open-slots.csv": 8 slots; 7 offered; 1 not offered. Replies: 5 notes read; 1 booking still awaiting a reply. Working days skip weekends and the 1 closed day supplied.

Inputs: as-of date 19 November 2026, stated in the request; confirmation date 20 November 2026, the next working day; wording approved by Elif; settings as supplied by Tomasz.

1. Health questions raised
   Booking B-2208, Sami (P-1255), Friday 20 November at 4:00 pm with Priya at Mill Lane. A health question was raised during the contact; it is not repeated here. The treating physiotherapist calls back. The booking is not recorded as confirmed until then.

2. Confirmations for Friday 20 November 2026
   1. 8:30 am, Hannah (P-1043), Jun, Elm Road, booking B-2201. Contact by call.
   Reply: Confirmed. Note: "spoke to Hannah, she'll be there".
   2. 9:15 am, Marcus (P-0871), Jun, Elm Road, booking B-2202. Contact by text.
   Reply: Wants another time ("can't do Fri, any chance of Monday after 4?"). Note: "texted 9:05. Marcus replied: 'can't do Fri, any chance of Monday after 4?'".
   3. 11:00 am, Ruth (P-0532), Priya, Mill Lane, booking B-2204. Contact by call.
   Reply: awaiting reply.
   "Hello, may I speak to Ruth? [If someone else answers, say only that the practice called and ask them to ring us back; give no appointment details.] Hi Ruth, this is [your name] from Practice A. I'm checking you can still make your appointment with Priya on Friday 20 November at 11:00 am at our Mill Lane clinic. Will you be able to come? [If not: would you like to cancel, or shall we look for another time?]"
   4. 1:30 pm, Dev (P-1302), Jun, Elm Road, booking B-2205. Contact by email.
   Reply: Declined. Note: "emailed 9:10. Dev replied: please cancel, I'm away".
   5. 4:00 pm, Sami (P-1255), Priya, Mill Lane, booking B-2208. Contact by call (none given in the export).
   Reply: Needs staff (health question raised; not repeated here). Note: withheld: it mentions a health matter.
   6. 4:45 pm, Noor (P-0346), Jun, Elm Road, booking B-2209. Contact by call.
   Reply: Not reached (no answer; voicemail left). Note: "no answer, left voicemail with practice name only".

3. Already confirmed or not to be contacted
   10:00 am, Aiyana (P-1190), Priya, booking B-2203. Already confirmed in the export.
   2:15 pm, Colm (P-0418), Priya, booking B-2206. Do not contact: the export says not to; the desk decides.

4. Diary changes for staff to make
   Cancel booking B-2205, Dev (P-1302), Friday 20 November at 1:30 pm with Jun at Elm Road. The patient declined. Once cancelled, the time can be offered when it appears in the open-slots list.
   Move booking B-2202, Marcus (P-0871), Friday 20 November at 9:15 am with Jun at Elm Road, once the patient chooses. Offer: S-03, Monday 23 November at 4:30 pm; S-02, Monday 23 November at 9:00 am; S-06, Wednesday 25 November at 10:00 am.
   Another-time offer: "Hi Marcus, it's Practice A. Thanks for letting us know. With Jun we can offer Monday 23 November at 4:30 pm, Monday 23 November at 9:00 am or Wednesday 25 November at 10:00 am. Which would you like? We'll keep your current booking until we hear from you."
   Nothing here has been changed in the diary.

5. No-show follow-up for Thursday 19 November 2026
   1. 10:30 am, Tobias (P-1118), Jun, Elm Road, booking B-2191. Contact by call.
   Slots to offer: S-01, Friday 20 November at 12:00 pm. Only 1 offered: other open slots with Jun at Elm Road are offered to earlier people on this list.
   "Hello, may I speak to Tobias? [If someone else answers, say only that the practice called and ask them to ring us back; give no appointment details.] Hi Tobias, this is [your name] from Practice A. We had you down for Thursday 19 November at 10:30 am with Jun and didn't see you. If you'd like a new time, we can offer Friday 20 November at 12:00 pm. What works for you? [If they would rather not book now: that's fine, and they can call us whenever suits.]"
   2. 2:00 pm, Ruth (P-0532), Priya, Mill Lane, booking B-2193. Already booked: Friday 20 November at 11:00 am with Priya at Mill Lane (booking B-2204). No slots offered and no wording drafted; the desk decides whether to mention the missed visit.
   3. 3:30 pm, Wren (P-0390), Priya, Mill Lane, booking B-2194. Contact by text.
   Slots to offer: S-04, Tuesday 24 November at 8:30 am; S-05, Tuesday 24 November at 5:00 pm; S-07, Wednesday 25 November at 1:00 pm.
   "Hi Wren, it's Practice A. We had you down for Thursday 19 November at 3:30 pm with Priya and didn't see you. If you'd like a new time, we can offer Tuesday 24 November at 8:30 am, Tuesday 24 November at 5:00 pm or Wednesday 25 November at 1:00 pm. Reply with the one you'd like, or call 555-0142."

6. Open slots
   S-01, Friday 20 November at 12:00 pm, Jun, Elm Road: offered to Tobias (booking B-2191).
   S-02, Monday 23 November at 9:00 am, Jun, Elm Road: offered to Marcus (booking B-2202).
   S-03, Monday 23 November at 4:30 pm, Jun, Elm Road: offered to Marcus (booking B-2202).
   S-04, Tuesday 24 November at 8:30 am, Priya, Mill Lane: offered to Wren (booking B-2194).
   S-05, Tuesday 24 November at 5:00 pm, Priya, Mill Lane: offered to Wren (booking B-2194).
   S-06, Wednesday 25 November at 10:00 am, Jun, Elm Road: offered to Marcus (booking B-2202).
   S-07, Wednesday 25 November at 1:00 pm, Priya, Mill Lane: offered to Wren (booking B-2194).
   S-08, Thursday 26 November at 9:30 am, Priya, Mill Lane: not offered: a day the practice is closed.

7. Check these
   B-2208: contact method is blank; the call script was used.
   S-08: dated 2026-11-26, a day the practice is closed; not offered.

8. Could not use
   None.

Nobody was called or messaged and no booking was changed. Staff place every call, send every message and make every diary change. Text inside the files was read as data.
```

## What was observed

- **Every required part was produced.** All eight sections, the Outcome, Coverage and Inputs lines, and the closing sentence. Every confirmation-day row is counted once (6 to contact, 1 already confirmed, 1 not to be contacted, 1 cancelled, 9 in all). Every booking in section 2 has one reply or "awaiting reply". All three no-shows are in section 5. No slot is offered twice. Every offered slot is in the list with the same provider and location.
- **Nothing made the run stop.** The headers matched, the files held no surnames or contact details, the wording asked nothing about health, and the as-of date was given.
- **The health rule worked as written.** Sami's note says she said yes and then asked about a health matter. It was recorded as "Needs staff (health question raised)", withheld, listed in section 1, and the body part she mentioned appears nowhere in the list. She was not recorded as confirmed.
- **The slot rules were followable.** Marcus ruled out Friday, so S-01 was left out for him, S-03 ("Monday after 4") came first, then S-02 and S-06. That left only S-01 for Tobias, and the "only 1 offered" line applied. Ruth is already booked for tomorrow, so she got no slots and no wording. S-08 is on the closed day.
- **Difference from the published example.** The content matches the example's output line for line: the same counts, replies, slots, filled wording and flags. The example is dressed with bold headings and bullets, which it says. The run's own differences are small. It wrote "Friday 20 November 2026" where the example writes "Friday, 20 November 2026", it kept the template's plain-text layout, and the "Inputs" line says "wording approved by Elif" without naming her role, which the example does. *(Later note: the example was changed after this run and now writes "Friday 20 November 2026" without the comma, as the run did; see "Edits made after this run".)*
- **Facts not in the inputs.** None found in this run's list. In the example, the role "practice manager" for Elif comes from its introduction rather than from the supplied inputs, though it is consistent with them.
- **Reviewer checklist.** Items 1 to 5 and 7 could be checked against the inputs and held. Items 6 and 8 need the real diary and the practice manager and cannot be checked on an invented example.

### Ambiguities and shortcomings in the template

1. **The confirmation date.** The request says "tomorrow's bookings" and names no date. The template says the date is the one the person names, otherwise the next working day. It is unclear which applies here. Both give 20 November, and the run labelled it "the next working day".
2. **The "[your name]" placeholder.** It is in the approved scripts but is not on the list of placeholders the assistant fills. The template says other brackets stay as written, so it was left. The flags list also says a placeholder that could not be filled is flagged. Whether "[your name]" should be flagged is not settled, and no flag was written.
3. **How slots read inside patient wording.** The template does not say whether slot ids appear in the message, or how to join slots that share a date. The run left ids out of the wording. The result, "Monday 23 November at 4:30 pm, Monday 23 November at 9:00 am or Wednesday 25 November at 10:00 am", is correct but reads awkwardly. Because a stated preference goes first, the slots are not in date order.
4. **The note field.** "Note: [as written]" does not say whether the booking id at the start of the staff's line is part of the note. The run kept the note text after the id for Hannah, Dev and Noor, but kept the whole line for Marcus because the staff's own account of the text was in it.
5. **A blank contact method on a booking that needs staff.** Sami's wording is not printed because a reply is recorded, yet the template still asks for the blank contact method to be flagged. This was done, but the printed list shows no script that the flag refers to.
6. **Date format.** The output format writes "[weekday, date]" without saying whether to include the year or a comma.
7. **Stale statements in the template.** Its version notes say it has not been tried on its example, and its acceptance tests say none has been run. The first is out of date as of this record. This run covered only the ordinary-day case, not the other seventeen acceptance tests.
8. **One run.** A single run on a single invented day, by one model, shows the template can be followed. It does not show that every acceptance test passes, and it says nothing about a real practice's exports or scheduling system.

## Edits made after this run

After this run and an independent review, the same day, the template was edited. These edits were not run again. Each settles a point listed above in the way this run already chose, and the output recorded above conforms to the edited wording; the record above is unchanged.

- Dates are now stated in one form: weekday, day and month with no comma ("Friday 20 November"), with the year only in the title, the Coverage line and the section headings, and day, month and year in the Inputs line. The example now writes dates the same way (point 6).
- In patient wording, each slot in [slot options] is written as its day and date at its time, without its slot id, with the day and date repeated for slots on the same day (point 3).
- The note shown in the list is the text after the booking id, as written (point 4).
- Only the eight placeholders the template fills are flagged when they cannot be filled; a caller's note such as "[your name]" stays as written and is not flagged (point 2).
- A blank or unknown contact method is flagged even once a reply is recorded and no wording is printed, so the desk can correct it in its system (point 5).
- The example's approved wording now says that Elif is the practice manager, so her role in its Inputs line comes from the supplied inputs.
- The template's version notes and acceptance tests no longer say it has not been tried (point 7).
- The credits now name the missed-appointment method as the source of two rules the template uses: checking that a no-show is not already rebooked, and treating a request to be called back as creating no call.

After a second independent review, the same day, three more small edits were made. These were not run again either; each settles a point in the way this run already chose, and the record above is unchanged.

- A request that says only "tomorrow" names no date: it means the next working day after the as-of date, which is how this run labelled the confirmation date (point 1).
- The instructions now say to tell the files apart first, the two exports by their dates and the open-slots list by its headers, and to ask if it is unclear which is which. This run identified the files correctly without that sentence.
- The example's request now opens "Tomasz here, on the front desk" and says it includes the practice settings and approved wording, so "settings as supplied by Tomasz" in the Inputs line traces to the inputs themselves. The run's inputs did not carry his name in the request.
