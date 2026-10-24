# School calendar PDF to ICS: a worked example

An original fictional school notice, its reviewed iCalendar file, and a checklist for checking an import. Use the pair when writing a tutorial, explaining calendar dates, or comparing a converter with a known reference.

**Start here:** [download the source PDF](https://raw.githubusercontent.com/cctanfujun/school-calendar-ics-example/main/school-dates.pdf), [download the reviewed ICS](https://raw.githubusercontent.com/cctanfujun/school-calendar-ics-example/main/school-dates.ics), or copy the [review checklist](https://github.com/cctanfujun/school-calendar-ics-example/blob/main/CHECKLIST.md).

These are invented Maple Ridge School dates for November–December 2026. They are not a real school's calendar. Import the sample into a separate test calendar, rather than your everyday calendar.

## What you can inspect

| File | Purpose |
| --- | --- |
| `school-dates.pdf` | One-page fictional source notice |
| `school-dates.ics` | Four reviewed events downloaded from the converter |
| `source-notice.txt` | Text extracted from the actual PDF for accessible inspection |
| `expected-events.json` | Expected local dates/times, the chosen time zone, and corresponding ICS values |
| `CHECKLIST.md` | A reusable review and import worksheet |
| `checksums.sha256` | SHA-256 checksums for the published files |

No application code, credentials, real school files, or user uploads are included.

## Four events to compare

The example uses **America/New_York**, selected during extraction. **The PDF does not specify a time zone.** This is explicit demonstration context, not information recovered from the notice. Resolve the correct time zone for your own document before importing timed events.

| Event | Local date | Local time | ICS start → end |
| --- | --- | --- | --- |
| School closed | 2026-11-02 | All day | `20261102` → `20261103` (`VALUE=DATE`) |
| Family evening | 2026-11-05 | 18:00–19:30, New York | `20261105T230000Z` → `20261106T003000Z` |
| Student showcase | 2026-12-04 | 13:00–14:00, New York | `20261204T180000Z` → `20261204T190000Z` |
| Term ends | 2026-12-18 | All day | `20261218` → `20261219` (`VALUE=DATE`) |

For an all-day event, `DTEND` is exclusive: November 2 ends at the start of November 3. For Family evening, the UTC end falls on November 6 while the local event still ends on November 5. “Term ends” records that one day; the notice does not specify a holiday range.

The downloaded ICS uses CRLF line endings and folded long lines. Keep the leading whitespace on continuation lines if you inspect or edit the raw file. Event UIDs identify these fictional example events; they are not account identifiers.

## Try the import

1. Compare the PDF, the table above, and `expected-events.json`.
2. Create a separate calendar such as “School dates example”.
3. In Google Calendar on a computer, open **Settings → Import & export**, choose the ICS, and select that separate calendar.
4. Check all four dates and times after importing. Your viewing time zone can change the display of timed events.
5. Remove the test calendar when finished. Re-importing a file can create duplicates; later changes to a PDF do not update previously imported events.

See the [complete illustrated guide](https://calendar.tanfujun.com/guides/school-pdf-to-google-calendar/) and [Google's import instructions](https://support.google.com/calendar/answer/37118?hl=en). If your school offers an official subscription or ICS, prefer that over converting its PDF.

## How this example was produced

I wrote the fictional notice for a demonstration of [PDF to Calendar](https://calendar.tanfujun.com/), the free beta I make. Its PDF-text path extracted these four events; I reviewed each event and downloaded the ICS. This pair was also used in a maker-run Google Calendar import demonstration. It is one checked example, not an accuracy benchmark, an AI extraction result, or an independent customer outcome. The converter's application code is maintained separately.

For your own document, the beta accepts one file, up to 3 PDF pages, 5 MB and 30 events. Extraction sends content to Cloudflare after consent; general layouts may use Workers AI. Review the selected events before exporting. The tool does not connect to calendar accounts or sync later changes.

## Reuse and corrections

The original example text, event data, and documentation are available under the [MIT License](https://github.com/cctanfujun/school-calendar-ics-example/blob/main/LICENSE). The license does not cover the converter's application code or online service. You can reuse the sample in tutorials and tests; retain its license notice. Descriptive credit is welcome, with no backlink or ranking-link requirement.

For a correction, open an issue describing the affected event, expected value, and calendar client. Use fictional or redacted examples; do not attach private school notices or personal calendars. The [checklist](https://github.com/cctanfujun/school-calendar-ics-example/blob/main/CHECKLIST.md) works without an upload or account with the converter.
