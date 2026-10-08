# Sending: from approved list to verified invitations

Only start this after the user approved the list in chat (SKILL.md, phase 4).

## Before the first send

- Confirm the logged-in account again (`https://www.linkedin.com/in/me/`). If it changed since phase 1, stop and ask.
- Reload the registry. Remove any approved prospect whose status or `account` changed since you loaded it, and tell the user.
- Count: never send more than the session cap, even if the user approved more. Offer to continue in a later session.

## Per prospect

1. **Reserve in the registry first:** status "Invitation sent", `account` = current account name, `sent_at` = now, `note` = final text, history entry. If the write fails, do not send.
2. **Open the profile URL.** Wait for the page to load. Check the name and headline match the prospect.
3. **Find the connect action.** LinkedIn shows it in one of two places:
   - a primary **Connect / Se connecter** button under the headline, or
   - inside the **More / Plus** menu next to "Message" and "Follow / Suivre".
   Open the menu if needed and pick **Connect / Se connecter**. Take a screenshot when unsure; button positions differ between profiles.
4. **Dialog "Add a note to your invitation?" / "Ajouter une note à votre invitation ?"**: confirm the dialog names the right person, then choose **Add a note / Ajouter une note**.
5. **Wait for the text box to be ready** (it may load for a second; typing too early types into nothing), then type the note.
6. **Verify before sending:** zoom on the dialog and check the text is complete and the counter is within the limit (for example "282/300"). If the box shows a lower limit than your note, stop and shorten the note, then show the change to the user if the meaning changed.
7. **Click Send / Envoyer.**
8. **Confirm the pending state:** the profile now shows "Pending / En attente" (sometimes only inside the More menu). If not, check the sent-invitations page before retrying. Never send twice.
9. **Pause a few seconds** before the next prospect. One profile at a time.

If any step fails: set the registry entry back to "To contact", clear `account`, add the reason to notes, and continue with the next prospect unless the failure is one of the stop conditions below.

## Stop conditions (stop the whole batch, hand back to the user)

- CAPTCHA, puzzle, "verify it's you", phone or email verification.
- "You've reached the weekly invitation limit" or any limit message.
- Warning about unusual activity, restriction, or terms violation.
- Logged out, or a different account appears.
- A dialog or page you do not recognize.
- A free-account prompt saying personalized notes are used up.

Never try to solve, bypass or work around these. Report what you saw, how many were sent, and what remains.

## After the batch

1. Open `https://www.linkedin.com/mynetwork/invitation-manager/sent/`, load the full list, and check that every reserved prospect appears with today's date.
2. Fix the registry for any mismatch.
3. Report to the user in a few lines: sent count, account used, skipped or failed (with reason), and when to withdraw stale invitations (about three weeks).

## Account health habits to share with the user (once, not every session)

- Keep sessions around 15 to 20 invitations per day per account, spread over the day.
- A low acceptance rate or people clicking "I don't know this person" hurts more than volume. Tight targeting and personal notes matter.
- Withdraw invitations still pending after about three weeks.
- Keep the LinkedIn profile complete (photo, clear headline, current role) before prospecting.

These are common practices, not official LinkedIn figures; LinkedIn does not publish its thresholds and they change.

## Login pitfalls (the user handles login, never you)

- **Passkey / "Insert your security key" system dialog:** the user clicks Cancel, then logs in with email and password.
- **"Sign in with Google" fails in an embedded browser:** Google often refuses embedded browsers. The user can set a LinkedIn password via "Forgot password?" (the Google sign-in keeps working elsewhere) and log in with email and password.
- **Two accounts, two computers:** each browser keeps its own LinkedIn session. Always identify the account by reading it (phase 1) so sends are attributed correctly.
