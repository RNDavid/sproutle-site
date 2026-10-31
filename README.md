# Sproutle website (privacy policy)

Google Play requires a privacy policy at a public web address for an app
that shows ads, and AdMob wants a website for its `app-ads.txt` file. These
files are that website: `index.html` (a short landing page) and
`privacy.html` (the policy).

## Before publishing: fill in the placeholders

Search both files for `[` and replace:

- `[DEVELOPER NAME]`: your name or studio name, as it will appear on Google Play.
- `[CONTACT EMAIL]`: an address you're happy to publish (Play also shows it).
- `[EFFECTIVE DATE]`: the date you publish the policy.
- `[CONFIRM AFTER CHOOSING THE PLAY CONSOLE TARGET AUDIENCE]`: once you pick
  the target audience in Play Console, keep the sentence after it if Sproutle
  is not aimed at children under 13 (and delete the marker); if it is, the
  policy and the ad settings both need changing first.

The policy describes what the app does today. If the app starts collecting
anything new (analytics, accounts, crash reporting, a new ad network),
update the policy before that release.

## Hosting on GitHub Pages (free)

The sproutle repo is private, and free GitHub Pages needs a public repo, so
use a separate small one:

1. On github.com: **New repository**, name `sproutle-site`, **Public**, add a README.
2. **Add file → Upload files**: drag in `index.html` and `privacy.html`, commit.
3. **Settings → Pages**: Source **Deploy from a branch**, branch `main`, folder `/ (root)`, Save.
4. After a minute the site is at `https://<your-github-name>.github.io/sproutle-site/`
   and the policy at `https://<your-github-name>.github.io/sproutle-site/privacy.html`.

Use the policy URL in Play Console (**App content → Privacy policy**) and the
site URL as the app's website in the store listing and in AdMob.

### app-ads.txt (after the AdMob account exists)

AdMob shows a one-line `app-ads.txt` for your account (**Apps → View all apps
→ app-ads.txt**). It must be at the *root* of the website listed on Google
Play. A GitHub Pages project site like the one above is not at a domain root,
so for app-ads.txt either use a user site (a repo named
`<your-github-name>.github.io`, whose files are served at the root), or a
custom domain. Ads still work without it; AdMob just warns and may limit
some demand. Decide when setting up AdMob.

## Play Console "Data safety" answers

These follow from what the app does (no data of its own leaves the device)
plus what the Google Mobile Ads SDK collects. Check them against Google's
current guide before submitting:
https://developers.google.com/admob/android/privacy/play-data-disclosure

- **Does the app collect or share user data?** Yes (the ads SDK does).
- **Data types collected and shared:**
  - Location: *Approximate location* (from IP address)
  - App activity: *App interactions* (ad interactions)
  - App info and performance: *Diagnostics*
  - Device or other IDs: *Device or other IDs* (advertising ID / app set ID)
- **Purposes:** Advertising or marketing; Analytics; Fraud prevention, security, and compliance.
- **Is data encrypted in transit?** Yes.
- **Can users request deletion?** The app stores nothing off the device; data
  held by Google is managed through Google's tools (answer as the form allows
  for SDK-collected data).
- Progress and settings are **not collected**: they never leave the device.
