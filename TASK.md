# Task: Rebuild index.html as a comprehensive ESTA-style application form

Read spec.csv for the full specification. The current index.html has the basic structure (step indicator, notice box, applicant info section). You need to rebuild it completely with ALL sections from the spec.

## Key Requirements:

1. **Input validation**: All text inputs accept ONLY English uppercase (a-z auto-converts to uppercase, Japanese/full-width blocked)
2. **Sections to add** (in order):
   - Applicant Info (already exists, needs validation updates)
   - Contact Info (email x2 with match validation, phone with country flag/code selector, phone type)
   - Address Info (postal code with search link, country, prefecture, city, street, building, room)
   - Passport Info (passport upload modal, selfie upload modal, passport number, issue date, expiry date)
   - Other passport/ID (yes/no toggle → issuing country, type, ID number, expiry)
   - Birth country/city
   - Current other nationality (yes/no → nationality, acquisition method)
   - Past other nationality (yes/no → nationality, acquisition date, abandonment date)
   - GE/NEXUS/SENTRI membership (yes/no → PASS ID)
3. **Each section** has a "?" help button that opens a modal with:
   - A screenshot preview of that section's fields (rendered as HTML mockup)
   - Explanatory text as specified
   - "×" close button
4. **Phone country codes**: Use emoji flags (🇯🇵 etc) with country code dropdown, JAPAN first
5. **Country lists**: Full world country lists as specified in the CSV (used for phone, address country, nationality, birth country, issuing country, past nationality, current other nationality)
6. **Nationality list for top section**: Only the 33 ESTA-eligible countries with JAPAN first
7. **Date selects**: Various date pickers with Day/Month/Year format for passport dates, nationality dates
8. **Bottom buttons**: "TOPへ戻る" and "選択項目の入力へ進む"
9. **Error messages**: Red text below fields when validation fails
10. **All in ONE HTML file** - inline CSS and JS

## Country list for phone/address/nationality dropdowns (full world list):
Use the lists from spec.csv. There are ~240 countries.

## Important details:
- Email fields: lowercase only, validate format, second field must match first
- Phone: digits only, show flag emoji, strip leading 0
- Postal code: digits only, 7 digits, link to Japan Post search
- Passport number: auto-uppercase, alphanumeric only
- Passport issue date: Day/Month/Year, years 2016-2026
- Passport expiry date: Day/Month/Year, years 2026-2036
- Other passport expiry: Year only dropdown 1900-2036, with UNKNOWN option
- ID number: auto-uppercase, alphanumeric, UNKNOWN option
- Past nationality dates: Day/Month/Year, years 1900-2026
- PASS ID: 9 digits only
- Birth date validation: cannot be in the future (show error at top of form)

Keep the existing design style (dark blue header, white cards, toggle tabs, etc).
