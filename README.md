# Diya & Jasdeep — Wedding Website

Live site: https://diyajasdeepwedding.vercel.app/

A single-page, responsive wedding website. Plain HTML, CSS and JavaScript — no build step. Deploy the folder as-is (Vercel, Netlify, any static host).

## Structure
```
audio/music.mp3   background music (starts after the loader; pauses on external links, resumes where it stopped)
index.html        all markup, styles (<style>) and scripts (<script>)
favicon.ico       browser-tab icon (circular DJ monogram)
fonts/            Bakelony (script) and Andrade Pro Bold (caps headings), WOFF
images/           photos, monogram, Ganesh icon, wardrobe illustrations, icons
```

## Sections
1. Hero · 2. Scratch-card date + invitation (couple & families) · 3. Our Moments · 4. Countdown to 26 Feb 2027, 6 PM IST · 5. Function Schedules · 6. Wardrobe Guide · 7. Venue · 8. Closing message · 9. RSVP · 10. Final (monogram + #herefortheDJ)

## Photos
Photos load by file name from `images/` (see `data-photo="..."` in index.html):

| File | Section |
| --- | --- |
| hero.jpg, hero-bg.jpg | Hero photo (shown at full sharpness) and its blurred side fill for wide screens |
| bride.jpg, groom.jpg | Meet the Bride / Groom |
| moment-1.jpg … moment-4.jpg | Our Moments (2 × 2) |
| invite.jpg | Invitation lace frame |
| detail-1.jpg, detail-2.jpg | Under Function Schedules |
| venue-ark.jpg, venue-gurudwara.jpg | Venue lace frames |
| closing-1.jpg | Closing message |
| wardrobe-*.jpg | Wardrobe Guide illustrations |

To swap a photo, replace the file with one of the same name. `data-pos` on each slot sets the crop focus (CSS object-position).

## Link preview & icons
- `images/wa-preview.jpg` (1200 × 630) is the image shown when the link is shared on WhatsApp, iMessage, Facebook, LinkedIn and X. The `og:` / `twitter:` tags in `<head>` point to it with the full live URL — update those URLs if the domain changes.
- `favicon.ico`, `images/favicon-*.png` are the browser-tab and home-screen icons.

## Settings (top of the `<script>` block)
- `HERO_VIDEO` — e.g. `'images/hero.mp4'` to use a video in the hero.
- `RSVP_ENDPOINT` — optional URL (Google Apps Script web app, Formspree, etc.). When set, RSVPs are POSTed there (Name, Attendance, Guests, Accompanying, Attending, Meal, Message). When empty, guests send their reply via WhatsApp or copy it.


## Fonts
Bakelony and Andrade Pro Bold are loaded from `fonts/`. Make sure your licences for both cover web embedding. Supporting fonts (Cormorant Garamond, Playfair Display, Montserrat, Pinyon Script fallback, Tiro Devanagari Sanskrit) load from Google Fonts.

## Editing tips
- Colours: `--green` (#38543d) and `--cream` / `--paper` in `:root`.
- Fonts: `--script` (Bakelony) and `--caps` (Andrade Pro) in `:root`.
- The scalloped dividers are pure CSS (`.edge.up` / `.edge.down`).
- The loader hides on the window `load` event (15 s safety timeout).

## Preview watermark
This copy shows a faint "PREVIEW" watermark (15% opacity) over the whole site.
To remove it, delete the line marked `preview watermark` just above `<audio id="bgm">`, and the `.pv-mark` rule at the end of the `<style>` block.
