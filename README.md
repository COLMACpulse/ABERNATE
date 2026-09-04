# abernate.com

Source for the public site at **https://abernate.com**.

One static page. No build step, no framework, no dependencies. What is in this
repository is exactly what is served.

---

## What is in here

| File | Served? | What it is |
|---|---|---|
| `index.html` | yes | The entire site. Structure, styles and content in one file. |
| `404.html` | yes | Shown for any unknown path. GitHub Pages picks this up by name. |
| `lockup.png` | yes | The full mark with wordmark and creed, recolored to steel for the dark ground. |
| `mark.png` | yes | The mark alone, used on the 404. |
| `favicon.png` | yes | The mark, squared and padded. |
| `robots.txt` | yes | Allows crawling and points at the sitemap. |
| `sitemap.xml` | yes | One entry. Enough for a single-page site. |
| `README.md` | no | This file. Visible to anyone browsing the repository, not part of the site. |

Fonts are the only external request the page makes.

---

## Deploying

1. Put these files in the repository root on the default branch.
2. **Settings → Pages → Build and deployment → Deploy from a branch**, pick that
   branch and the `/ (root)` folder.
3. The site is live at `https://<account>.github.io/<repo>/` within a minute.

That is the whole thing. No build, no action, no workflow file.

---

## Later, when the domain is ready

There is deliberately **no `CNAME` file here**. A `CNAME` in the repository with no
DNS behind it makes GitHub try to serve the custom domain, fail, and take the
github.io address down with it. So it is left out until the DNS exists.

When you get to it:

1. At the DNS host, delete the default parking records first. They will fight
   yours. Then point the apex at GitHub's four addresses and the `www` label at
   `<account>.github.io.` Confirm the current addresses against GitHub's own
   documentation rather than any copy of them, including this one.
2. **Settings → Pages → Custom domain**, type `abernate.com`, Save. GitHub creates
   the `CNAME` file itself at that moment. Set it there, not by hand, so the file
   and the setting cannot disagree.
3. Tick **Enforce HTTPS** once it stops being greyed out.

---

## Before it goes live

**`hello@abernate.com` must be forwarding.** The page has exactly one call to
action and it is that address. A site that collects nothing and answers nowhere is
worse than no site.

---

## Editing the page

Everything lives in `index.html`. The palette is at the top of the stylesheet:

```css
--ground:#0F1215;   /* background */
--panel:#171C21;    /* the run block */
--steel:#E3E7EB;    /* text and the mark */
--muted:#8B949E;    /* secondary text */
--line:#252C33;     /* hairlines */
```

There is no accent color anywhere, and that is a decision rather than an
omission. The mark is monochrome metal, and the page emphasizes by weight,
inversion and space instead of by hue. A traffic-light palette on a page about
refusal would read as a dashboard, which this is not.

Three rules the page is built on, worth keeping if you edit it:

- **The hero is a real run, verbatim.** It is the shipped sample mission with
  release requested, and it shows the mission passing every operational check and
  still not shipping. If the engine's output changes, the block changes with it.
  Nothing on this page is transcribed from a document.
- **Every number is measured.** The test count, the Python version and the
  forgery table come from running the package, not from quoting a brief. When the
  one-pager and the technical brief disagreed on the forgery count, the measured
  figure won.
- **"What it is not" and "Before you spend time on this" carry the same visual
  weight as everything else.** The product is sold on refusing to overstate, so
  burying the disclosures would contradict it.

---

## Rights

Proprietary work product of Range Art and Design LLC (CA 202359212028), trading as
COLMACpulse.

**No open-source license is granted.** There is no `LICENSE` file in this
repository and that is deliberate, not an oversight: absent one, default copyright
applies and all rights are reserved. The absence of a license is not permission.

This repository contains the marketing page only. It does not contain the ABERNATE
asset, its source, or any part of it.
