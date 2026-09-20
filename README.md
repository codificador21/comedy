# Comedy portfolio sites

Five single-page portfolio websites for Indian stand-up comedians. Plain HTML, CSS and JavaScript —
no build step, no dependencies, no webfonts, no third-party scripts until a video is played.

**Live:** https://codificador21.github.io/comedy/

| Site | Theme | Link |
|---|---|---|
| Kaustubh Agarwal | Dark circuit | https://codificador21.github.io/comedy/kaustubh-agarwal/ |
| RJ Vidit (Vidit Sharma) | Retro FM radio | https://codificador21.github.io/comedy/rj-vidit/ |
| Pratyush Chaubey | Desi pop | https://codificador21.github.io/comedy/pratyush-chaubey/ |
| Rohit Singh | Minimal editorial | https://codificador21.github.io/comedy/rohit-singh/ |
| Rajat Sood | Velvet &amp; gold | https://codificador21.github.io/comedy/rajat-sood/ |

## Structure

```
<slug>/
  index.html     the whole site: markup, CSS and JS in one file
  notes.md       every source URL, plus what could NOT be verified
  images/        locally saved images + 640w and 960w variants for srcset
```

## What each site has

Hero, about, animated-counter stats, specials and videos (click-to-load YouTube), upcoming shows
with ticket links, brand work or credits, gallery, booking form and social links.

## Technical notes

- **Mobile-first.** No horizontal overflow at 360px. The nav collapses to one horizontally
  scrollable row below 900px, tap targets are at least 46px, form fields are 16px so iOS does not
  zoom on focus, and safe-area insets are respected on notched phones.
- **Responsive images.** Every photo ships at 640w / 960w / original with `srcset` and `sizes`.
  Everything below the fold is lazy-loaded; only the hero image is eager.
- **SEO.** Semantic landmarks, one `h1` per page, unique title and description, canonical URL,
  Open Graph and Twitter cards with absolute image URLs, `Person` JSON-LD (plus an `Event` list for
  Rajat Sood's dated shows), and alt text on every image.
- **Motion.** Scroll reveals, hero line-rise, counters and hover states, all disabled under
  `prefers-reduced-motion: reduce`.
- **Video.** Nothing loads from YouTube until you click. Opened from `file://`, videos open in a new
  tab instead, because YouTube will not embed into a null origin.
- **Forms** are front-end only. Four open a pre-filled `mailto:`; RJ Vidit's copies the enquiry to
  the clipboard, because he publishes no booking address.

## Sourcing and status

Every factual claim traces to a public source listed in that site's `notes.md`, together with the
source URL for each saved image and an explicit list of what could not be verified (follower counts
read from search snippets, unconfirmed TV credits, and so on).

These are **unofficial demo portfolios**, not official artist websites, and every footer says so.
They are not affiliated with, authorised by or endorsed by any of the comedians featured.
Photographs remain the copyright of their owners.

## Local preview

```sh
python3 -m http.server 8777
# http://localhost:8777/
```
