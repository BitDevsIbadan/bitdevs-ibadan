# BitDevs Ibadan

The website for **BitDevs Ibadan**, a monthly Socratic seminar for people who want to dig into Bitcoin and Lightning, from protocol details to the tooling around them.

Every month we meet, talk through a list of topics, and publish the notes, links, and photos here. Anyone can help keep the archive accurate by opening a pull request.

## How the site works

- It's built with [Astro](https://astro.build).
- Each meetup is one folder of Markdown plus photos in `src/content/meetups/`.
- Every merge into `main` goes live automatically, and every pull request gets its own preview link.

```
src/content/meetups/
  2026-10-silent-payments/
    index.md        <- notes, links, date
    cover.jpg       <- photos live next to the notes
    group.jpg
```

## Run it locally

You need [Node.js](https://nodejs.org) 22 or newer.

```sh
npm install
npm run dev      # starts a local preview at http://localhost:4321
npm run build    # builds the final site into dist/
```

## Contributing

To add meetup notes, fix a typo, or improve the site, read [CONTRIBUTING.md](CONTRIBUTING.md). Please also follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

The code is released under the [MIT License](LICENSE). Meetup notes and photos belong to their authors and are shared for the community's reference.
