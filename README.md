# Cat-a-log — public site

The two pages App Store Connect requires a URL for. No build step, no
dependencies, no external requests (CSS is inline, the icon is local), so they
behave exactly as they look here.

- `index.html` — **Support URL**: contact + FAQ
- `privacy.html` — **Privacy Policy URL**: also linked from the app's paywall
- `icon.png` — favicon + header image (copy of `AppIcon.appiconset/icon-light.png`)

## Source of truth

`../privacy-policy.md` is authoritative for the policy's wording. `privacy.html`
is its published rendering — **edit the markdown first**, then mirror it here, or
the two drift and the public page becomes the wrong one.

## Publishing (GitHub Pages)

These files are versioned here, next to the policy they render, but they get
published from a **separate public repo**: free GitHub Pages requires a public
repo, and this one carries the internal security reviews in `docs/`, including
still-open findings.

1. Use a public repo holding **only** these files. `Cat-a-log-app/cat-a-log` was
   empty when this was written, so it works — just never push the app source into
   it, or everything above becomes public too.
2. Easiest path, no terminal: repo → **Add file → Upload files** → drag the four
   files in → **Commit changes**.
3. Settings → Pages → Source: **Deploy from a branch**, Branch: **main**,
   Folder: **/ (root)** → Save.
4. Verify **while logged out** (private window) — Apple rejects a policy URL that
   asks for a login.

Expected addresses for that repo:

- `https://cat-a-log-app.github.io/cat-a-log/` → support
- `https://cat-a-log-app.github.io/cat-a-log/privacy.html` → privacy policy

## Where the URLs go

| URL | Used by |
|---|---|
| the support page | ASC → App Information → Support URL |
| `…/privacy.html` | ASC → App Privacy → Privacy Policy URL, **and** the app's paywall |

The paywall also needs a Terms of Use link, and Apple's standard EULA needs no
hosting: `https://www.apple.com/legal/internet-services/itunes/dev/stdeula/`
