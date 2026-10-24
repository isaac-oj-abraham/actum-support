# actum privacy and support pages

This folder contains the two static pages published by the GitHub Actions workflow:

- `index.html` — privacy policy
- `support.html` — support information and contact email

The pages are generated from `UnifiedProductivity/Resources/PrivacyPolicy.md` and `UnifiedProductivity/Resources/PrivacyContact.json` by running:

```sh
python3 scripts/export_privacy_site.py
```

To publish, push the repository's `main` branch to GitHub, then open **Settings → Pages** and set the build and deployment source to **GitHub Actions**. The workflow deploys this folder. After the first successful run, GitHub shows the site's base URL under **Settings → Pages**. The policy is at that base URL; support is at `support.html` under it.

Add those final HTTPS URLs to `UnifiedProductivity/Resources/PrivacyContact.json`, regenerate the pages, and run `python3 scripts/export_privacy_site.py --check-ready` before treating the links as release-ready. Re-run the generator after changing the policy or contact details.
