# linkedin-agent-claude

A skill that turns Claude into a LinkedIn prospecting agent for **your** business.

You say who you target and what you offer. Claude finds qualified prospects, checks each one for real (website, decision-maker, LinkedIn profile), writes a personal connection note that reads like you wrote it, logs everything in a shared registry, and, once you approve the list, sends the invitations from your own LinkedIn account.

[Version française](README.fr.md)

## What it does

1. **Setup.** First run: two questions (who do you target, what do you offer). Claude saves your answers and creates a registry. It then reads which LinkedIn account is logged in, so every invitation is attributed to the right person.
2. **Research.** Searches by region and segment, opens each prospect's website, identifies the decision-maker in official company registers, confirms their LinkedIn profile. Candidates that fail verification are dropped, not padded in.
3. **Writing.** One note per prospect, built on one verified detail, your main offer first, one simple question at the end. Strict rules against AI-sounding phrasing and templated repetition.
4. **Approval.** You see the full list with every note. Nothing is sent until you say go.
5. **Sending.** For each prospect: reserve it in the registry, open the profile, send the invitation with its note, confirm it is pending. Then a final check against LinkedIn's sent-invitations page and a short report.

Built for teams: two people prospecting from two LinkedIn accounts share one registry and never invite the same person twice. Each row shows which account contacted it.

## Example

> Find 20 padel clubs in Belgium and Switzerland that need a better booking setup, and prepare the invitations.

> Lance 15 invitations parmi les prospects "À contacter".

> Marie accepted, draft a follow-up.

## Requirements

- Claude with skills enabled: claude.ai (paid plan with code execution) or Claude Code.
- A browser tool Claude can drive in your logged-in session: the browser built into the Claude desktop app, the Claude in Chrome extension, or another browser automation tool. Without one, the skill still researches and writes, but you send manually.
- Web search.
- Optional: Artifacts with a database (claude.ai) for a shared registry page. Otherwise the registry is a CSV file.

## Install

**claude.ai:** download this repository as a zip, keep only the `skills/linkedin-agent` folder, zip that folder, and upload it in Settings (Features / Skills section). The exact menu can change; see Anthropic's documentation on Agent Skills.

**Claude Code:** copy `skills/linkedin-agent` to `~/.claude/skills/` (all projects) or `.claude/skills/` (one project).

Then just ask Claude to prospect. The skill triggers on its own.

## Safety rules built in

- Claude never types your password or any code. You log in yourself.
- Nothing is sent without your explicit approval of the exact list.
- Default cap: 20 invitations per session per account.
- Claude stops and hands back control on any CAPTCHA, verification, limit or warning screen. It never tries to bypass them.
- Every fact in a note must have been verified on a real source.

## Important: LinkedIn's terms and your account

**Read this before using the sending step.**

LinkedIn's User Agreement prohibits using bots or other unauthorized automated methods to add contacts or send messages. Having an AI agent click "Connect" and "Send" in your browser falls under that rule. LinkedIn can restrict or close accounts that break it, and it does not publish its detection thresholds.

This skill reduces the risk (low volume, human approval, personal notes, stop on any warning), but **it cannot remove it**. You use the automated sending at your own risk, on your own account. If you want zero automation risk, stop at the approval step and send the invitations yourself using the notes Claude prepared.

## Data protection

Prospecting professionals in the EU (GDPR) or elsewhere means processing personal data. Keep to professional information, have a legitimate interest you can explain, honor opt-out requests (mark the prospect "No follow-up" and never contact them again), and do not collect private contact details. This is general information, not legal advice.

## Repository layout

```
skills/linkedin-agent/
├── SKILL.md                     the method Claude follows
├── references/
│   ├── onboarding.md            first-run questions and config
│   ├── research.md              finding and verifying prospects
│   ├── writing-rules.md         human-sounding notes, banned phrases, self-review
│   ├── sending.md               step-by-step sending, stop conditions, login pitfalls
│   └── registry.md              registry options, fields, config format
└── assets/
    └── registry-template.csv    CSV header for the file-based registry
```

## License

MIT. See [LICENSE](LICENSE).

This project is independent and is not affiliated with, endorsed by or sponsored by Anthropic or LinkedIn. "Claude" is a trademark of Anthropic; "LinkedIn" is a trademark of LinkedIn Corporation.
