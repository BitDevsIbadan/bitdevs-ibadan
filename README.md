# BitDevs Ibadan

A [Zola](https://www.getzola.org) site for hosting the topics and links from BitDevs Ibadan meetups, past and future.

## Development

You'll need [Zola](https://www.getzola.org/documentation/getting-started/installation/) to run the site locally. Once it's installed:

* Clone the repository and go into the directory
* Run `zola serve --drafts`
* Go to http://localhost:1111

## Making a Post

To make a new post, add a file to the `content` directory named `YYYY-MM-DD-socratic-seminar-N.md`. The date in the file name is the meetup date. At the top of the file you must provide the following information:

```md
+++
title = "Socratic Seminar #N"
template = "post.html"
[extra]
luma = "<optional Luma event link>"
+++
```

After that, it's just simple [Markdown](https://www.markdownguide.org/cheat-sheet/). The site generates the rest, including the venue, map and directions. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

## Upcoming and Recent Events

The home page sorts meetups by date: today or later goes under Upcoming Events, earlier goes under Recent Events. The visitor's browser rechecks this against their own date, so a meetup moves to Recent the day after it happens, even if nobody has pushed. If there's no post for the next meetup yet, the site shows the last Saturday of the month on its own.

## Changing Site Data

All site configuration, including social links and the venue, lives in `config.toml`.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Attributions

Thanks to [BitDevs NYC](https://github.com/BitDevsNYC/BitDevsNYC.github.io) for the original Jekyll site, to [BitDevs LA](https://bitdevsla.org) for the Zola BitDevs template, and to [BitDevs Abuja](https://github.com/BitDevsAbuja/bitdevsabuja.org) whose site this one follows.

## License

The code is released under the [MIT License](LICENSE).
