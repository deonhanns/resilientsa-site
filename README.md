# ResilientSA — public website

Static, no build step, no framework. Plain HTML, one shared stylesheet, real design tokens from the Living Soil system. Ten pages, mobile-first, no JavaScript except a CSS-only checkbox for the mobile nav.

## Status

**Not deployed.** Built and ready, but held back until the NPC is actually registered, so the site opens saying something true, not "coming soon." See `about.html` / `progress.html` for the reasoning.

**Hosting undecided.** Vercel's Hobby plan is non-commercial use only. Confirm this site (and any linked payment or licensing activity) qualifies before deploying there — otherwise Vercel Pro or another host. Not resolved in this repo.

## Real gaps, stated plainly, not hidden in code comments

1. **The contact form uses `mailto:`, and that's a real weakness, not just a placeholder.** It opens the visitor's email app pre-filled. That works fine for a funder or a Grounder, who likely has email configured. It's a poor fit for a community member on a basic phone whose main app is WhatsApp, who may see a broken or empty compose screen instead. Before this goes live for community outreach specifically, worth deciding between: a real form backend (e.g. Formspree, or a small serverless function once there's a backend to put it on), or a direct WhatsApp link as the primary contact method for that one audience. Not decided here. The address it points to (`hello@resilientsa.org.za`) is a placeholder — it doesn't exist yet and needs to be created (or replaced) before the form is real.
2. **Privacy notice (`privacy.html`) has bracketed placeholders** — Information Officer, retention period, complaints address, analytics stance. Marked in the page itself. Needs an attorney's review, not just filling in blanks, before any form actually collects real data.
3. **No analytics, no cookies, nothing tracking visitors.** Intentional for now, matches the privacy notice's current honest "not yet decided" stance. Add deliberately, not by default, if that changes.
4. **The About page hero photo** (`assets/img/about-hero.jpg`) is a real photograph, duotoned into the brand palette, credited in-page ("Photo: Claire, via Pexels") and in the corner overlay. Sourced and cleared per the project's photography selection guide — see that guide before adding more real photography anywhere else on the site.
5. **Every other page uses original illustrated art**, not photography — deliberate, not a placeholder waiting to be replaced. See the design system's README for why.

## Structure

- `index.html`, `platform.html`, `train.html`, `communities.html`, `grounders.html`, `funders.html`, `about.html`, `progress.html`, `contact.html`, `privacy.html`, `glossary.html`, `listen.html`
- `assets/styles.css` — every design token as a CSS custom property, plus responsive layout rules
- `assets/img/` — the real favicon (from the actual brand mark), and the About page's photo

## Podcast (added, needs real IDs before it's live)

- Five `.podcast-embed` Spotify embeds, one on each of `index.html`, `funders.html`, `grounders.html`, `train.html`, `platform.html`, each matched to the page's audience (Foundation, Funders, Grounders, Training Tracks, The App).
- A new `listen.html` hub page lists all five in sequence, for anyone arriving via a shared link or Spotify rather than organically. Linked from every page's nav as "Listen".
- **Every embed currently points at a placeholder ID** (`SPOTIFY_EPISODE_ID_EP1` through `EP5`), marked with a `<!-- TODO (Deon): ... -->` comment right above each `<iframe>`. Find-and-replace each with the real Spotify episode ID from the show's dashboard before this is live. The "Follow on Spotify" button on `listen.html` also needs the real show URL — it's currently `href="#"`.
- The Training Tracks page (`train.html`) now shows a third card, **Build & Shelter Skills**, styled muted/dashed (`.card.pending`) with an "In development" badge and no call-to-action — the Delft/Home of Compassion partnership isn't confirmed. Don't restyle it to match the other two tracks, and don't add a CTA to it, until that partnership is actually confirmed.

## Running it locally

No build step. Open `index.html` directly, or serve the folder with any static server, e.g. `python3 -m http.server`.
