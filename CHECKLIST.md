# School calendar import checklist

Copy this worksheet when reviewing a school PDF and its calendar file. You can use it with any converter or a manual workflow.

## Before converting

- [ ] Check whether the school already provides an official calendar subscription or ICS. Prefer it when available.
- [ ] Confirm the school year, date format, named months, excluded dates, and which students each event applies to.
- [ ] Identify all-day events and timed events separately.
- [ ] Confirm the school or event's time zone. If it is missing, ask rather than guess.

## Review each event

- [ ] Compare every title and date with the source, including dates across a year boundary.
- [ ] Check start and end times, multi-day boundaries, and any stated recurrence or exceptions.
- [ ] Keep missing or ambiguous information unresolved until it is confirmed.
- [ ] Do not turn isolated dates into a continuous date range.
- [ ] For all-day ICS events, remember that `DTEND` is the first day after the event.
- [ ] Check that a UTC time falling on another date still represents the intended local date and time.
- [ ] Remove events for other classes or groups and check for omissions.

| Source event / page | Intended local date(s) | All day or local time | Confirmed time zone | Open question | Checked |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |

## Import and compare

- [ ] Keep the original document and the reviewed ICS.
- [ ] Create a separate test calendar and check the destination before importing.
- [ ] Compare the resulting events with the source, including dates, time zones and multi-day ends.
- [ ] If an event seems missing, check the destination calendar's visibility and the event's actual year before importing again.
- [ ] If Google reports “Processed zero events”, check whether the first import already added the events; consult its [import troubleshooting](https://support.google.com/calendar/answer/45654?hl=en) instead of repeatedly importing.
- [ ] Check for duplicates before re-importing. A one-time import does not sync later changes to the PDF.
- [ ] Remove the test calendar when finished; do not delete an unrelated or primary calendar.

For a completed example, inspect the [fictional source PDF](https://raw.githubusercontent.com/cctanfujun/school-calendar-ics-example/main/school-dates.pdf) and its [reviewed ICS](https://raw.githubusercontent.com/cctanfujun/school-calendar-ics-example/main/school-dates.ics). The [illustrated guide](https://calendar.tanfujun.com/guides/school-pdf-to-google-calendar/) walks through Google Calendar's desktop import.

Written by Fujun Tan, maker of [PDF to Calendar](https://calendar.tanfujun.com/). This checklist does not require that tool. See the repository's MIT License for reuse.
