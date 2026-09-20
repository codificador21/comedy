# codificador21 / comedy

Landing page for my web development work, plus a set of private client demo sites.

**Live:** https://codificador21.github.io/comedy/

## Layout

```
index.html    landing page - what I build and how to reach me
404.html      shown for any address that does not resolve
<client>/     one self-contained demo site per client
  index.html  the whole site: markup, CSS and JS in one file
  notes.md    every source URL, plus what could not be verified
  images/     local images + 640w / 960w variants for srcset
```

## Client demos are unlisted

Each demo lives on its own unguessable path and carries `noindex, nofollow`. They are deliberately
**not linked from the landing page and not listed here**, so that sharing one link with one person
does not hand them everyone else's work in progress.

> Note: on GitHub Free, Pages can only publish from a **public** repository, so the directory names
> in this repo are visible to anyone who finds it. The paths are unguessable and the pages are kept
> out of search engines, which stops casual URL-poking, but it is not a substitute for real access
> control. Hosting from a private repo (Cloudflare Pages, Netlify, or GitHub Pro) would close that gap.

These demos are **unofficial**, built from publicly available sources for portfolio purposes. They
are not official artist websites and are not affiliated with or endorsed by anyone featured. Every
site's footer says so, and its `notes.md` lists every source and every unverified claim.

## Technical notes

- **Mobile-first.** No horizontal overflow at 360px. Nav collapses to one horizontally scrollable
  row below 900px, tap targets are at least 46px, form fields are 16px so iOS does not zoom on
  focus, and safe-area insets are respected on notched phones.
- **Responsive images.** Every photo ships at 640w / 960w / original with `srcset` and `sizes`.
  Everything below the fold is lazy-loaded; only the hero image is eager.
- **SEO.** Semantic landmarks, one `h1` per page, unique title and description, canonical URL,
  Open Graph and Twitter cards with absolute image URLs, and `Person` JSON-LD.
- **Motion** respects `prefers-reduced-motion: reduce`.
- **Video.** Nothing loads from YouTube until you click.
- **No build step, no dependencies, no webfonts, no third-party scripts.**

## Local preview

```sh
python3 -m http.server 8777
# http://localhost:8777/
```
