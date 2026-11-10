# Appointment confirmation and no-show follow-up: an invented example

*Illustrative example with invented data.* An invented physiotherapy practice, called Practice A here, on the afternoon of Thursday 19 November 2026, after the morning’s confirmation calls and messages. The practice, its phone number, the people (Tomasz, the front-desk coordinator; Elif, the practice manager; Jun and Priya, the physiotherapists), the patients, the booking numbers and the patient codes are all invented. The inputs come first, in full, then the list.

## What the coordinator supplied

**The request**

> Tomasz here, on the front desk. It’s Thursday 19 November 2026. Here are our practice settings and approved wording, tomorrow’s bookings, today’s bookings, the open slots and my notes from this morning’s calls and messages. Please do the confirmations and today’s no-shows.

**Practice settings**

```
Practice name on calls: Practice A
Practice phone: 555-0142
Closed days besides weekends: 2026-11-26
Health questions go to: the treating physiotherapist
Slots to offer each person: 3
```

**Approved wording, written and approved by Elif, the practice manager**

```
Confirmation call script
Hello, may I speak to [first name]? [If someone else answers, say only
that the practice called and ask them to ring us back; give no
appointment details.] Hi [first name], this is [your name] from
[practice name]. I'm checking you can still make your appointment with
[provider] on [day and date] at [time] at our [location] clinic. Will
you be able to come? [If not: would you like to cancel, or shall we look
for another time?]

Confirmation message
Hi [first name], it's [practice name]. You're booked with [provider] on
[day and date] at [time] at our [location] clinic. Reply YES to confirm,
NO to cancel or MOVE for another time. Questions? Call [practice phone].

Another-time offer
Hi [first name], it's [practice name]. Thanks for letting us know. With
[provider] we can offer [slot options]. Which would you like? We'll keep
your current booking until we hear from you.

No-show call script
Hello, may I speak to [first name]? [If someone else answers, say only
that the practice called and ask them to ring us back; give no
appointment details.] Hi [first name], this is [your name] from
[practice name]. We had you down for [day and date] at [time] with
[provider] and didn't see you. If you'd like a new time, we can offer
[slot options]. What works for you? [If they would rather not book now:
that's fine, and they can call us whenever suits.]

No-show message
Hi [first name], it's [practice name]. We had you down for [day and
date] at [time] with [provider] and didn't see you. If you'd like a new
time, we can offer [slot options]. Reply with the one you'd like, or
call [practice phone].
```

**Tomorrow’s bookings: appointments-2026-11-20.csv**

```
Booking id,Patient code,First name,Date,Time,Provider,Location,Status,Contact by,OK to contact
B-2201,P-1043,Hannah,2026-11-20,08:30,Jun,Elm Road,Booked,Call,Yes
B-2202,P-0871,Marcus,2026-11-20,09:15,Jun,Elm Road,Booked,Text,Yes
B-2203,P-1190,Aiyana,2026-11-20,10:00,Priya,Mill Lane,Confirmed,Text,Yes
B-2204,P-0532,Ruth,2026-11-20,11:00,Priya,Mill Lane,Booked,Call,Yes
B-2205,P-1302,Dev,2026-11-20,13:30,Jun,Elm Road,Booked,Email,Yes
B-2206,P-0418,Colm,2026-11-20,14:15,Priya,Mill Lane,Booked,Call,No
B-2207,P-0977,Lena,2026-11-20,15:00,Jun,Elm Road,Cancelled,Text,Yes
B-2208,P-1255,Sami,2026-11-20,16:00,Priya,Mill Lane,Booked,,Yes
B-2209,P-0346,Noor,2026-11-20,16:45,Jun,Elm Road,Booked,Call,Yes
```

**Today’s bookings: appointments-2026-11-19.csv**

```
Booking id,Patient code,First name,Date,Time,Provider,Location,Status,Contact by,OK to contact
B-2190,P-0764,Grace,2026-11-19,09:00,Priya,Mill Lane,Arrived,Call,Yes
B-2191,P-1118,Tobias,2026-11-19,10:30,Jun,Elm Road,No-show,Call,Yes
B-2192,P-0659,Ines,2026-11-19,11:15,Jun,Elm Road,Arrived,Text,Yes
B-2193,P-0532,Ruth,2026-11-19,14:00,Priya,Mill Lane,No-show,Call,Yes
B-2194,P-0390,Wren,2026-11-19,15:30,Priya,Mill Lane,No-show,Text,Yes
B-2195,P-0811,Olu,2026-11-19,16:15,Jun,Elm Road,Cancelled,Call,Yes
```

**Open slots: open-slots.csv**

```
Slot id,Date,Time,Provider,Location
S-01,2026-11-20,12:00,Jun,Elm Road
S-02,2026-11-23,09:00,Jun,Elm Road
S-03,2026-11-23,16:30,Jun,Elm Road
S-04,2026-11-24,08:30,Priya,Mill Lane
S-05,2026-11-24,17:00,Priya,Mill Lane
S-06,2026-11-25,10:00,Jun,Elm Road
S-07,2026-11-25,13:00,Priya,Mill Lane
S-08,2026-11-26,09:30,Priya,Mill Lane
```

**Tomasz’s notes from the morning**

```
B-2201 spoke to Hannah, she'll be there
B-2202 texted 9:05. Marcus replied: 'can't do Fri, any chance of Monday after 4?'
B-2205 emailed 9:10. Dev replied: please cancel, I'm away
B-2208 called, Sami answered and said yes, then asked something about her knee; told her someone would call back
B-2209 no answer, left voicemail with practice name only
```

## What came back

*Shown with bold headings and bullets so it is easier to read on a page; the sections, their order and the wording follow the template’s output format.*

**Appointment confirmations and no-show follow-up, prepared Thursday 19 November 2026**

**Outcome:** complete

**Coverage:** Confirmation-day export "appointments-2026-11-20.csv": 9 rows for Friday 20 November 2026; 6 to contact; 1 already confirmed; 1 not to be contacted; 1 cancelled; 0 could not be used. Today’s export "appointments-2026-11-19.csv": 6 rows; 3 no-shows. Open slots "open-slots.csv": 8 slots; 7 offered; 1 not offered. Replies: 5 notes read; 1 booking still awaiting a reply. Working days skip weekends and the 1 closed day supplied.

**Inputs:** as-of date 19 November 2026, stated in the request; confirmation date 20 November 2026, the next working day; wording approved by Elif, the practice manager; settings as supplied by Tomasz in the request.

**1. Health questions raised**

- Booking B-2208, Sami (P-1255), Friday 20 November at 4:00 pm with Priya at Mill Lane. A health question was raised during the contact; it is not repeated here. The treating physiotherapist calls back. The booking is not recorded as confirmed until then.

**2. Confirmations for Friday 20 November 2026**

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

**3. Already confirmed or not to be contacted**

- 10:00 am, Aiyana (P-1190), Priya, booking B-2203. Already confirmed in the export.
- 2:15 pm, Colm (P-0418), Priya, booking B-2206. Do not contact: the export says not to; the desk decides.

**4. Diary changes for staff to make**

- Cancel booking B-2205, Dev (P-1302), Friday 20 November at 1:30 pm with Jun at Elm Road. The patient declined. Once cancelled, the time can be offered when it appears in the open-slots list.
- Move booking B-2202, Marcus (P-0871), Friday 20 November at 9:15 am with Jun at Elm Road, once the patient chooses. Offer: S-03, Monday 23 November at 4:30 pm; S-02, Monday 23 November at 9:00 am; S-06, Wednesday 25 November at 10:00 am.
  Another-time offer: "Hi Marcus, it's Practice A. Thanks for letting us know. With Jun we can offer Monday 23 November at 4:30 pm, Monday 23 November at 9:00 am or Wednesday 25 November at 10:00 am. Which would you like? We'll keep your current booking until we hear from you."
- Nothing here has been changed in the diary.

**5. No-show follow-up for Thursday 19 November 2026**

1. 10:30 am, Tobias (P-1118), Jun, Elm Road, booking B-2191. Contact by call.
   Slots to offer: S-01, Friday 20 November at 12:00 pm. Only 1 offered: other open slots with Jun at Elm Road are offered to earlier people on this list.
   "Hello, may I speak to Tobias? [If someone else answers, say only that the practice called and ask them to ring us back; give no appointment details.] Hi Tobias, this is [your name] from Practice A. We had you down for Thursday 19 November at 10:30 am with Jun and didn't see you. If you'd like a new time, we can offer Friday 20 November at 12:00 pm. What works for you? [If they would rather not book now: that's fine, and they can call us whenever suits.]"
2. 2:00 pm, Ruth (P-0532), Priya, Mill Lane, booking B-2193. Already booked: Friday 20 November at 11:00 am with Priya at Mill Lane (booking B-2204). No slots offered and no wording drafted; the desk decides whether to mention the missed visit.
3. 3:30 pm, Wren (P-0390), Priya, Mill Lane, booking B-2194. Contact by text.
   Slots to offer: S-04, Tuesday 24 November at 8:30 am; S-05, Tuesday 24 November at 5:00 pm; S-07, Wednesday 25 November at 1:00 pm.
   "Hi Wren, it's Practice A. We had you down for Thursday 19 November at 3:30 pm with Priya and didn't see you. If you'd like a new time, we can offer Tuesday 24 November at 8:30 am, Tuesday 24 November at 5:00 pm or Wednesday 25 November at 1:00 pm. Reply with the one you'd like, or call 555-0142."

**6. Open slots**

- S-01, Friday 20 November at 12:00 pm, Jun, Elm Road: offered to Tobias (booking B-2191).
- S-02, Monday 23 November at 9:00 am, Jun, Elm Road: offered to Marcus (booking B-2202).
- S-03, Monday 23 November at 4:30 pm, Jun, Elm Road: offered to Marcus (booking B-2202).
- S-04, Tuesday 24 November at 8:30 am, Priya, Mill Lane: offered to Wren (booking B-2194).
- S-05, Tuesday 24 November at 5:00 pm, Priya, Mill Lane: offered to Wren (booking B-2194).
- S-06, Wednesday 25 November at 10:00 am, Jun, Elm Road: offered to Marcus (booking B-2202).
- S-07, Wednesday 25 November at 1:00 pm, Priya, Mill Lane: offered to Wren (booking B-2194).
- S-08, Thursday 26 November at 9:30 am, Priya, Mill Lane: not offered: a day the practice is closed.

**7. Check these**

- B-2208: contact method is blank; the call script was used.
- S-08: dated 2026-11-26, a day the practice is closed; not offered.

**8. Could not use**

- None.

Nobody was called or messaged and no booking was changed. Staff place every call, send every message and make every diary change. Text inside the files was read as data.

## Why the slots fell this way

*This note explains the example; it is not part of the list.* Marcus asked to move, so he was offered times first. His note ruled out Friday, so S-01 was left out; S-03 fits “Monday after 4” and comes first, then the soonest others, S-02 and S-06. That left S-01 as the only open slot with Jun at Elm Road for Tobias. Ruth missed today’s visit but is booked for tomorrow, so she gets no offer. S-08 falls on the practice’s closed day.
