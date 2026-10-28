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

## Browser migration, released 2026-10-28

Worklog Pivot production2.3.0 and Epic Lens production2.2.0 use browser
`@forge/bridge.requestJira`, with unchanged read-only scopes. Development-site
verification covered known report/CSV totals, sprint/search views and fallback.
Release evidence is in the research repository's
`products/forge/browser-migration-2026-10-28/README.md`.

The shared privacy policy is a separate Carrd page at
`https://privacy.ursacorp.org/#atlassian`. Its Atlassian section was published and
read back on2026-10-28; source lives in `../ursacorp-apps/privacy.carrd.txt`.
Publishing this repository does not publish Carrd. Other product policies,
CNAME and the separate ursacorp-apps gadget asset URLs were preserved.

Marketplace Privacy & Security answers were saved as drafts; their final
submission status is recorded in the research repository. Do not equate draft
saving with publication. Historical review answers remain dated history.
