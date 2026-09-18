# capbudgetmobile

Static GitHub Pages host for the CapBudget mobile app's public-facing pages —
nothing here talks to CapBudget's main codebase, which stays private on
purpose.

## Get the app

CapBudget's source is private, so it isn't on the Play Store. Get the signed
APK with automatic updates via **[Obtainium](https://github.com/ImranR98/Obtainium)**:

[![Get it on Obtainium](https://img.shields.io/badge/Get_it_on-Obtainium-D96F44?style=for-the-badge)](https://galaticlag.github.io/capbudgetmobile/download.html)

Or grab the APK directly from the [Releases](https://github.com/galaticlag/capbudgetmobile/releases)
page.

## Pages

Three pages, published via GitHub Pages (Settings → Pages → `main` / `/ (root)`):

- **`download.html`** — the "Get CapBudget" page above, with a one-tap
  "Add to Obtainium" link (uses Obtainium's `obtainium://app/` deep-link
  format via their redirect page, so it still works for visitors who don't
  have Obtainium installed yet).
- **`index.html`** — the OAuth/PSD2 consent redirect bounce page for
  CapBudget's mobile Open Banking (Enable Banking) integration. It holds no
  logic beyond forwarding the browser to the app's own `com.capbudget.app://`
  URL scheme — no data is read, stored, or processed here. It exists only
  because Enable Banking requires an `https://` redirect URL and rejects a
  custom app scheme directly. The page URL is registered as the "Allowed
  redirect URL" in the household's own Enable Banking application, and as
  `REDIRECT_URI` in CapBudget's own `bankConnections.js` view.
- **`privacy.html`** — the app's privacy policy, linked from the Play Store /
  App Store listings. Kept in sync manually with the canonical copy in the
  main (private) repo — see that repo's `CLAUDE.md` for the sync checklist.
