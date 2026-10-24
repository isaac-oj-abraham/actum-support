# actum privacy and support pages

This folder contains the two static pages published by the GitHub Actions workflow:

- `index.html` — privacy policy
- `support.html` — support information and contact email

The pages are generated from `UnifiedProductivity/Resources/PrivacyPolicy.md` and `UnifiedProductivity/Resources/PrivacyContact.json` by running:

```sh
python3 scripts/export_privacy_site.py
```

To publish, push the repository's `main` branch to GitHub, then open **Settings → Pages** and set the build and deployment source to **GitHub Actions**. The workflow deploys this folder. After the first successful run, GitHub shows the site's base URL under **Settings → Pages**. The configured policy URL is `https://isaac-oj-abraham.github.io/actum-support/`; support is at `https://isaac-oj-abraham.github.io/actum-support/support.html`.

The HTTPS URLs are configured in `UnifiedProductivity/Resources/PrivacyContact.json`. Run `python3 scripts/export_privacy_site.py --check-ready` after policy or contact changes. The readiness check validates URL format, not whether the pages are publicly reachable; verify both links after deployment.
