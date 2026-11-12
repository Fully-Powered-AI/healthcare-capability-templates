# Appointment confirmation and no-show follow-up

The front desk gets tomorrow’s bookings from the appointment export with the practice’s approved script or message filled in for each, every reply recorded once staff have called, and today’s no-shows with open slots to offer them. Staff make every call and every diary change.

*Workflow template · Healthcare · Customer support and service · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/appointment-confirmation-and-no-show-follow-up/)*

## The outcome

Your front desk starts each confirmation round with the whole of tomorrow on one list: who to call, who to text, who has already confirmed and who the practice has been asked not to contact. Every booking carries the exact words your practice approved, with the patient’s first name, the day, the time and the place already filled in, so whoever is on the desk says the same thing the same way.

After the calls, the same list records each answer: coming, not coming, wants another time, not reached. A message left on voicemail never counts as confirmed. The cancellations and moves become a short list of diary changes for staff to make. Today’s no-shows each get a few open slots from your own list, never one offered to two people at once, and the follow-up words to use.

The work stays administrative. Nobody is asked about symptoms or the reason for a visit, and if a patient raises a health question it is passed to the person your practice names, with the detail kept out of the list.

## Who starts the work, and when

The front-desk coordinator or scheduling coordinator starts it each working day: in the morning for the next day’s confirmations, and again in the afternoon with the replies and the day’s no-shows. Anyone covering the desk can run it the same way. The practice manager writes the wording once and owns the settings.

## What they supply

- Tomorrow’s bookings and today’s bookings, exported from your scheduling system as spreadsheet files, with patients shown by first name and a patient code.
- Your list of open slots.
- Your practice’s approved wording: a confirmation call script, a confirmation message for text and email, an offer of another time, a no-show call script and a no-show message.
- After the calls, a line from staff for each booking saying what happened.
- Your settings: the practice name as said on calls, your phone number, the days you are closed, who calls back on health questions and how many slots to offer each person.

No phone numbers, surnames or visit reasons are needed: staff contact patients from your own system. If an export’s column headings do not match what the template expects, it stops and asks rather than guessing.

## What comes out

One list in a fixed order, opening with an outcome line and a coverage line that counts every booking read and says what could not be used. Then health questions to pass on, tomorrow’s confirmations, the bookings not to contact, the diary changes, today’s no-show follow-up, every open slot and who it is offered to, and the points to check by hand.

Every section is always present, so an empty one reads “None” and a missing file reads “Not checked”, never as a clean result. The list calls no one, sends nothing and changes no booking. It ends by saying so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Healthcare](https://fullypowered.ai/industries/healthcare/): the front desk of a medical, dental or therapy practice that confirms the next day’s appointments and follows up the ones missed today.
- [Professional services](https://fullypowered.ai/industries/professional-services/): any firm whose day runs on booked appointments with clients.
- [Education](https://fullypowered.ai/industries/education/): tutoring and lesson providers who confirm sessions and rebook the ones missed.
- [Customer support and service](https://fullypowered.ai/functions/customer-support-and-service/): the daily contact with people about their bookings, done in approved words.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a confirmation routine that lives in one coordinator’s habits becomes one anyone covering the desk can run.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a practice with a working diary, a long-serving desk and no written routine.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): a practice adding providers or sites faster than the desk can keep track of who has confirmed.

## What has to change for your company

Your wording comes first: the template carries none of its own and never writes words for a patient. The practice manager writes the five pieces once, with each call script asking for the patient before giving any detail. Then match the column headings to your scheduling system’s export, and add your closed days and who calls back on health questions.

Several rules are our editorial choices, and your practice manager should confirm or change each: the next working day is the default day to confirm; a voicemail or a text with no reply is not a confirmation; slots are offered with the same provider at the same location; patients who asked to move are offered times before no-shows; a no-show who is already rebooked gets no offer; the list never suggests a missed-appointment fee or a discharge. The complete list is in the template.

Use it only in an AI product your practice has approved for this information. For the neighbouring work, see [Prior-authorization follow-up list](https://fullypowered.ai/workflows/prior-authorization-follow-up-list/) for requests waiting on payers and [Customer reply drafting](https://fullypowered.ai/workflows/customer-reply-drafting/) for written replies.

## What has been checked

Fully Powered AI wrote this workflow template in its own words, drawing on two published MIT-licensed methods credited in its sources. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it, and lists the small edits made afterward that have not been run again. That run covered an ordinary day, with a voicemail, a request to move, a health question and a no-show already rebooked; it did not reach a column heading that does not match, a file carrying contact details, wording that asks why a visit was missed, or a request to send the messages. It has not been tested in a practice, and no practice manager has reviewed its rules. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your practice means running it on a past week your desk already knows, with cases written in advance: a voicemail, a patient who asks to move with a preferred day, a reply that mentions a health question, a no-show who is already rebooked, two people waiting for the same provider. The coordinator checks every filled script and every slot against the diary before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Prior-authorization follow-up list](../prior-authorization-follow-up-list/)
- [Customer reply drafting](https://fullypowered.ai/workflows/customer-reply-drafting/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
