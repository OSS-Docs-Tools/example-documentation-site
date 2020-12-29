## An example app

This repo uses [`@oss-docs/sync`](https://www.npmjs.com/package/@oss-docs/sync) to keep some locale specific files (you can find those in [`OSS-Docs-Tools/example-localization-repo`](https://github.com/OSS-Docs-Tools/example-localization-repo)).

```sh
git clone https://github.com/OSS-Docs-Tools/example-documentation-site
cd example-documentation-site

# Normal dep installs
yarn install

# Grab localizations
yarn docs-sync pull OSS-Docs-Tools/example-localization-repo#main 0

# Go
yarn start
```

## What is happening here?

When you clone the repo, it only contains the markdown files for english docs.

```sh
> tree docs
docs
└── en
    ├── doc1.md
    ├── doc2.md
    └── root.m
```

Then running: `yarn docs-sync pull OSS-Docs-Tools/example-localization-repo#main 0`

`Et voilà` - it pulls in the other languages

```sh
> tree docs
docs
├── en
│   ├── doc1.md
│   ├── doc2.md
│   └── root.m
└── fr
    └── doc1.md
```

This repo uses a `.gitignore` to ignore any directory in the `docs` dir _except_ for en:

```sh
# Remove all of the docs dir
**/docs/*

# Except for the english folder
!**/docs/en
```

----

# Website

This website is built using [Docusaurus 2](https://v2.docusaurus.io/), a modern static website generator.

### Installation

```
$ yarn
```

### Local Development

```
$ yarn start
```

This command starts a local development server and open up a browser window. Most changes are reflected live without having to restart the server.

### Build

```
$ yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

### Deployment

```
$ GIT_USER=<Your GitHub username> USE_SSH=true yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
