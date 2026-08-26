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
