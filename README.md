# capbudgetmobile

Static GitHub Pages host for the CapBudget mobile app's public-facing pages —
nothing here talks to CapBudget's main codebase, which stays private on
purpose. Two pages:

- **`index.html`** — the OAuth/PSD2 consent redirect bounce page for
  CapBudget's mobile Open Banking (Enable Banking) integration. It holds no
  logic beyond forwarding the browser to the app's own `fr.capbudget.app://`
  URL scheme — no data is read, stored, or processed here. It exists only
  because Enable Banking requires an `https://` redirect URL and rejects a
  custom app scheme directly. Once GitHub Pages is enabled (Settings → Pages →
  Deploy from a branch → `main` / `/ (root)`), the resulting page URL is
  registered as the "Allowed redirect URL" in the household's own Enable
  Banking application, and as `REDIRECT_URI` in CapBudget's own
  `bankConnections.js` view.
- **`privacy.html`** — the app's privacy policy, linked from the Play Store /
  App Store listings. Kept in sync manually with the canonical copy in the
  main (private) repo — see that repo's `CLAUDE.md` for the sync checklist.
