# Contributing to BitDevs Ibadan

Thanks for helping out. There are three common ways to contribute:

1. **Add notes for a meetup** (the most common)
2. **Fix something**, like a typo, a broken link, or a wrong date
3. **Improve the site**, like its design, pages, or accessibility

You don't need to be a web developer for the first two.

## Adding notes for a meetup

Each meetup gets its own folder under `src/content/meetups/`, named `YYYY-MM-short-topic`:

```
src/content/meetups/2026-10-silent-payments/
  index.md
  cover.jpg
  group.jpg
```

Copy this into `index.md` and fill it in:

```md
---
title: "Socratic Seminar #12"
date: 2026-10-24
summary: "Silent payments, the mempool policy debate, and a Lightning bug postmortem."
cover: ./cover.jpg
coverAlt: "Attendees around the table at the October meetup"
topics:
  - title: "Silent payments (BIP 352)"
    links:
      - https://github.com/bitcoin/bips/blob/master/bip-0352.mediawiki
  - title: "Mempool policy debate"
    links:
      - https://bitcoinops.org/
photos:
  - src: ./group.jpg
    alt: "Group photo after the session"
---

Short write up of what we discussed and any questions left open for next time.
```

### Rules for photos

- **Get consent** from anyone clearly identifiable before posting their photo. The git history keeps files forever, even after you delete them.
- **Keep each photo under about 500KB.** Resize to around 1600px wide before committing. [Squoosh](https://squoosh.app) does this in the browser.
- **Always write alt text**, a short description of the photo for people using screen readers.
- Use `.jpg` for photos and lowercase file names with no spaces.

### Rules for notes

- Link to primary sources where you can, like BIPs, mailing list posts, or PRs.
- Don't attribute opinions to named people unless they're fine with it. We use the Socratic format so people can think out loud.

## Making the change

**On GitHub, without installing anything:**

1. Go to `src/content/meetups/` on GitHub and choose **Add file → Create new file**.
2. Type `2026-10-your-topic/index.md` as the name. The slash creates the folder.
3. Paste and fill in the template, then choose **Propose changes**.
4. Upload photos into the same folder with **Add file → Upload files**.
5. Open the pull request.

**Locally:**

```sh
git checkout -b notes/2026-10
npm install
npm run dev          # preview at http://localhost:4321
npm run build        # make sure it builds before you push
git add src/content/meetups/2026-10-your-topic
git commit -m "notes: add October 2026 meetup"
git push origin notes/2026-10
```

Then open a pull request. Two things happen automatically:

- **The CI check** builds the site. If your frontmatter is missing a field, the check fails and tells you which one.
- **A preview link is posted** as a comment on the pull request. Open it to see exactly how your notes and photos will look before anything goes live.

## Code changes

- Open an issue first for anything bigger than a small fix so we can agree on the approach.
- Keep pull requests focused on one change.
- Make sure `npm run build` passes.
- Keep the site light: no backend, no tracking scripts, and only add JavaScript where a page needs it.

## Commit messages

Use a short prefix so the history stays easy to scan:

- `notes:` for meetup content
- `fix:` for bug fixes
- `feat:` for new pages or features
- `docs:` for README or guide changes
- `chore:` for dependencies and tooling

## Questions

Open an issue or ask at the next meetup.
