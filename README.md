# Check — Early Access Confirmation Email

Email sent to users right after they join the Check early access waitlist.

## Files

| File | Purpose |
|---|---|
| `check-early-access-email.html` | **Production. This is the file to send.** Images load from GitHub Pages. |
| `preview.html` | Visual review only. **Do not send.** Images are embedded as base64, which Gmail and most clients block. |
| `check-logo.png`, `signature.png`, `instagram-icon.png` | Image assets (3x). Served from GitHub Pages at `https://jetdesigns.github.io/Check-Email-HTML/<file>`. |

## Trigger

Send after the waitlist row is **successfully inserted into Supabase**, not on form submit. If the insert fails, do not send.

## Merge tag

`Hi {{first_name}}!` — replace `{{first_name}}` with the ESP's merge syntax. Always set a fallback (e.g. `there`) so the email never renders `Hi !` when the name is empty.

## Links

- Instagram button: `https://www.instagram.com/workwithcheck/`

## Hosting

Images depend on GitHub Pages being enabled for this repo (Settings → Pages → Deploy from branch `main`, `/root`). Do not rename, move, or delete the image files, or the production email will show broken images.

## Still to decide (product, not dev)

- **Subject line:** TBD
- **Sender name and address:** TBD

## Before shipping

- Send test emails to Gmail (web + mobile), Apple Mail, and Outlook.
- Check that images load and that the signature's alt text ("The Check team") shows when images are blocked.
