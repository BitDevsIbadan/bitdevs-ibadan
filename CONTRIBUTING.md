# Contributing to BitDevs Ibadan

Thanks for helping out. The most common contributions are:

1. **Posting the topics for a meetup**
2. **Fixing something**, like a typo, a broken link, or a wrong date
3. **Suggesting a topic** for the next seminar, by opening an issue
4. **Improving the site**, like its design or accessibility

You don't need to be a web developer for the first three.

## Posting a meetup

Each meetup is one Markdown file in `content/`, named with the meetup date:

```
content/2026-10-31-socratic-seminar-1.md
```

Start the file with this block, then list the topics in Markdown:

```md
+++
title = "Socratic Seminar #1"
template = "post.html"
[extra]
luma = "https://lu.ma/your-event"
+++

### Announcements

Short welcome note, thanks to sponsors and hosts.

---

### Mailing List Posts

* [Title of the post](https://groups.google.com/g/bitcoindev/...)

---

### Bitcoin Core

* [Title of the pull request](https://github.com/bitcoin/bitcoin/pull/...)
```

The venue, map and directions are added automatically from `config.toml`, so you don't need to repeat them in each post. `luma` is optional; leave it out if there's no event page.

Use the same sections as other BitDevs chapters where they fit: General News, Mailing List Posts, Delving Bitcoin Posts, Bitcoin Core, Lightning, and so on. To prepare a meetup in advance without publishing it, add `draft = true` under `template` and remove it when it's ready. Until a post is published, the home page shows the next last Saturday of the month as the upcoming meetup on its own.

### Rules for topics

- Link to primary sources where you can, like BIPs, mailing list posts, or pull requests.
- We follow the [Chatham House Rule](https://www.chathamhouse.org/about-us/chatham-house-rule): don't attribute what was said at a meetup to a named person.

## Making the change

**On GitHub, without installing anything:**

1. Go to the `content` folder on GitHub and choose **Add file → Create new file**.
2. Name it `YYYY-MM-DD-socratic-seminar-N.md`.
3. Paste and fill in the template above, then choose **Propose changes** and open the pull request.

**Locally:**

```sh
git checkout -b post/seminar-1
zola serve --drafts      # preview at http://localhost:1111
zola check --skip-external-links
git add content/2026-10-31-socratic-seminar-1.md
git commit -m "post: add Socratic Seminar #1"
git push origin post/seminar-1
```

Then open a pull request. Two things happen automatically:

- **The CI check** builds the site. If the file name or the block at the top is wrong, the check fails.
- **A preview link is posted** as a comment on the pull request. Open it to see exactly how the page will look before anything goes live.

## Code changes

- Open an issue first for anything bigger than a small fix so we can agree on the approach.
- Keep pull requests focused on one change.
- Make sure `zola build` passes.
- Keep the site light: no tracking scripts, and only add JavaScript where a page needs it.
- Templates live in `templates/`, styles in `sass/`, and colors for light and dark mode at the top of `sass/style.scss`.

## Commit messages

Use a short prefix so the history stays easy to scan:

- `post:` for meetup pages
- `fix:` for bug fixes
- `feat:` for new pages or features
- `docs:` for README or guide changes
- `chore:` for tooling and dependencies

## Questions

Open an issue or ask at the next meetup.
