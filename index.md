---
title: Home
nav_order: 1
---

<h1>BPS Wiki</h1>{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## About

TODO: about section

---

## Contributing

Any submissions of self created content must include a `.md` file describing the
content. Whether you're adding a simple schematic library or an in depth tutorial,
it needs to have a dedicated page so people can find it. Unfinished articles are
allowed, as along as they are marked as such.

If you're just adding a link to a book or another website, then that can simply
be added to the `index.md` file of the appropriate category.

### Adding an Article

1. Make a fork of this repository on [GitHub].
2. Add your article as a `.md` file in the appropriate folder. If a folder does
   not exist, create one with the name of an existing category. If the category
   does not exist, create the category as well.
3. Add any asserts (pictures, schematic files, etc.) to a folder with the name
   of the article in the same parent folder. If the article is
   `/electronics/pyro-channels.md`, then an asset will be placed in
   `/electronics/pyro-channels/schematic1.png`.
4. Submit a pull request to the main repo and include a short description of
   your changes

[github]: https://github.com/BPS-space/bps-space.github.io

### Technical Details

The contents of the wiki are open source so anyone can add to and improve on the
wiki. The contents are written in markdown and rendered using jekyll. If you want
to contribute to the wiki, it may be a good idea to read the below links.

-   [Theme Docs](https://pmarsceill.github.io/just-the-docs/)
-   [Jekyll](https://jekyllrb.com/docs/)
-   [Github Pages Docs](https://help.github.com/en/github/working-with-github-pages)

If you have the VSCode editor, local development of the wiki can be made much easier.
The repository is set-up with a dev-container so that you do not have to install
jekyll or deal with ruby.

-   [VS Code Dev-Containers](https://code.visualstudio.com/docs/remote/containers)

There are vscode tasks setup to build and locally test the wiki as well.
