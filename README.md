# ursacorp-docs

Documentation site for the URSACORP apps for Jira Cloud, served at
**https://docs.ursacorp.org**.

Built for Atlassian's Marketplace review requirement that each listing's
documentation link point at a page covering how the app works, its features, and
setup, usage and verification steps.

## Why this is a separate repository

`uson1x/ursacorp-apps` cannot host it. That repository's GitHub Pages output is
what serves `blog.theivan.io/ursacorp-apps/assets/*.png`, and those URLs are
hardcoded as gadget thumbnails in the Forge manifests of two live apps. Giving
that repository a custom domain would move those assets and break the gadget
picker icons in apps that are under review.

## Layout

```
index.html                    hub, linking all four apps
issue-aging-chart/index.html
epic-lens/index.html
sprint-countdown/index.html
worklog-pivot/index.html
style.css                     shared, theme-aware
CNAME                         docs.ursacorp.org
```

## DNS

`docs.ursacorp.org` must be a CNAME to `uson1x.github.io`. The apex
`ursacorp.org` stays on Carrd and is untouched.

## Marketplace

Each app listing's Documentation URL should point at its own page here, not at
the hub.

## Browser migration documentation, prepared 2026-10-28

The Worklog Pivot and Epic Lens pages, hub and security policy have a prepared
update for browser `@forge/bridge.requestJira` transport. The two app pages and
security page record verified development deployment and pending production release. Do not remove that marker
until the deployed versions and relevant older major versions have been checked.
Development versions were verified on 2026-10-28. Production release and the
public documentation readback must be recorded separately.

The shared privacy policy is a separate Carrd page at
`https://privacy.ursacorp.org/#atlassian`. Its paste-ready Atlassian section lives
in `../ursacorp-apps/privacy.carrd.txt`; publishing this repository does not
publish that policy. Preserve the site's other product sections. Replace the
policy's effective date on publication. The canonical Carrd page was published
and read back on 2026-10-28.

For release: verify the two apps on the owned Jira site; record Forge versions
and remaining resolver-bearing versions; finalize the status notes; publish the
canonical policy and this GitHub Pages site; then read back all affected URLs.
Keep the CNAME and the separate `ursacorp-apps` gadget asset URLs unchanged.
Update the Marketplace Privacy & Security responses and app-specific review
answers to match the verified deployment. Their prepared text is maintained in
the research repository's `products/forge/SECURITY-QUESTIONNAIRE-ANSWERS.md` and
`products/forge/MARKETPLACE-REVIEW-ANSWERS.md`.
