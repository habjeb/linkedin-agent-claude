# Research: finding and verifying prospects

The quality of the whole session depends on this phase. A note can only be personal if the facts behind it are real.

## 1. Plan the search

Turn the config's target into 3 to 6 concrete angles before searching. Good angles:

- **Geography split:** one angle per country, region or city cluster.
- **Trigger events:** recently opened, recently taken over, expanding to a second site, hiring, event announced.
- **Visible need signals:** no website, broken or outdated website, booking or ordering only through a generic third-party platform, contradictory info online.
- **Sub-segments:** independent vs. chains (usually skip chains), size bands.

When the session can run sub-agents, give each one an angle and the same brief (below), run them in parallel, then merge.

## 2. Brief for each candidate

For every candidate, collect:

| Field | How to get it |
|---|---|
| Company / organization name | Search results, directories, maps listings |
| Location | Same |
| Website | Open it. Write "NONE" only after two different searches found nothing |
| What you saw on the site | Concrete and factual: "copyright 2017, menu links all go to home page", "booking button opens a WhatsApp group", "site returns HTTP 500 and shows spam links". Never infer a defect you did not see |
| Current tools (if visible) | Booking or ordering platform linked from the site. For internal use only: never name it in notes |
| Decision-maker | Full name and role, from an official source |
| Source for the decision-maker | URL of the register, legal notice or article |
| One positive, verifiable detail | Number of courts/shops/employees, opening date, event, award, expansion |
| Concrete need | One sentence linking what you saw to the user's offer |
| Confidence | high / medium / low, with the reason when not high |

## 3. Official sources for decision-makers

Prefer registers over guesses. By country:

- **France:** annuaire-entreprises.data.gouv.fr, pappers.fr, societe.com, the site's "mentions légales" (legally required, often names the publication director).
- **Belgium:** kbopub.economie.fgov.be (BCE/KBO), pappers.be.
- **Switzerland:** zefix.ch, moneyhouse.ch; the site's "Impressum".
- **Germany / Austria:** the site's "Impressum" (legally required), handelsregister.de, firmenbuch.at.
- **UK:** find-and-update.company-information.service.gov.uk (Companies House).
- **Elsewhere:** the national business register, then local press.

If the legal representative is a holding company, find the person behind it and mark confidence "medium".

## 4. Confirm the LinkedIn profile

Do this in the logged-in browser, one search at a time, at a normal pace:

1. Search LinkedIn people for the person's name plus the company name.
2. If that returns nothing, search the company name alone (people list their employer), then the name alone and filter by location.
3. Accept a match only when the headline, current position or experience mentions the company, or the location and role match unambiguously. Open the profile when in doubt.
4. Record the profile URL in its canonical form (`https://www.linkedin.com/in/<slug>/`).
5. If several people run the business, prefer the one in 2nd degree (shared connections raise acceptance), then the most active profile.

If no profile can be confirmed, keep the candidate out of the sending list and mention it in a short "verified but not on LinkedIn" list; the user may reach them by email or phone.

## 5. Deduplicate

Before presenting, remove every candidate whose LinkedIn URL, company or domain is already in the registry or the config's exclusions. Normalize URLs (decode, lowercase, strip accents and query strings) before comparing.

## 6. What not to do

- Do not scrape or bulk-export LinkedIn data, and do not collect personal emails or phone numbers from LinkedIn.
- Do not pad the list. Fewer good prospects beat a full list of weak ones.
- Do not present a defect you did not observe, or a decision-maker you did not source.
