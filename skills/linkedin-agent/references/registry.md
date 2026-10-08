# Registry: the shared source of truth

The registry records every prospect, its status, its note and, above all, **which LinkedIn account contacted it**. It prevents two team members from inviting the same person and keeps the config between sessions.

Pick the first option the session supports. Tell the user which one you chose and where it lives.

## Option A: shared page with a database (claude.ai with Artifacts)

Use when the session offers a published page with a shared database (an Artifact with the `db` capability; load the `artifact-capabilities` skill first if it exists).

- Build a simple page: header with counters (to contact / sent / accepted, and sent per account), filters (status, account, country), one card per prospect with name (linked to the LinkedIn profile), company, location, need, website, the note with a Copy button, a status selector, notes, and an "Account" badge.
- Include a "Who am I" selector so humans changing a status are recorded too, and record the account automatically when a status first moves away from "To contact".
- Store prospects in collection `prospects`, document id = normalized LinkedIn slug (`p-<slug>`), and the config in collection `config`, document `main`.
- The page is private by default: tell the user to share it (edit access) with every team member who prospects.

## Option B: CSV file (any environment with file access)

Use `assets/registry-template.csv` as the header. Keep the file in a folder the user chose (a project folder, or a synced drive). Save the config as `linkedin-agent.config.json` next to it.

With a CSV, warn the user once: two people editing the same file at the same time can overwrite each other. One person at a time, or move to option A or a shared spreadsheet.

## Option C: shared spreadsheet through a connector

If a spreadsheet connector (Google Sheets, Excel online) is connected, the same columns work there and handle concurrent edits.

## Fields

| Field | Meaning |
|---|---|
| `id` | `p-` + LinkedIn slug, lowercase, accents removed, non-alphanumerics replaced by `-` |
| `linkedin_url` | Canonical profile URL |
| `name` | Name as shown on LinkedIn |
| `company` | Company or organization |
| `location` | City, region, country code |
| `segment` | Sub-segment from the target |
| `website` | URL, or `NONE` |
| `site_findings` | What you actually saw on the site |
| `need` | One-sentence concrete need |
| `decision_maker_source` | URL proving the role |
| `confidence` | high / medium / low |
| `note` | The connection note (final text actually sent) |
| `status` | To contact, Invitation sent, Accepted, In discussion, Meeting set, Won, No follow-up |
| `account` | LinkedIn account that sent the invitation (empty until sent). Never overwritten afterwards |
| `status_by` | Person who last changed the status |
| `status_at` | Date of last status change (ISO 8601) |
| `sent_at` | Date the invitation was sent |
| `batch` | Label of the session, for example "Batch 3, padel BE (2026-10-08)" |
| `notes` | Free text: replies, follow-ups, reasons for failure |
| `history` | Optional log of status changes with who and when |

## Config document

```json
{
  "target": "padel clubs in FR, CH, BE; owners or managers",
  "offer": "club management app: bookings, POS, marketing; no booking commission",
  "secondary_offer": "website creation or redesign when their site needs it",
  "brand_in_notes": "product brand only",
  "language": "prospect's language",
  "tone": "professional, direct",
  "session_cap": 20,
  "exclusions": ["competitor-a.com", "Existing Client Ltd"],
  "never_say": ["the prospect's current software name", "prices"],
  "team": ["Marie", "Paul"]
}
```

## Rules

- Read the registry at the start of the session and again right before each send.
- Reserve (status "Invitation sent" + `account`) before clicking Send; roll back if the send fails.
- Never delete rows. A prospect who said no stays as "No follow-up" so nobody contacts them again.
- Never put passwords, session cookies or personal contact data scraped from LinkedIn in the registry.
