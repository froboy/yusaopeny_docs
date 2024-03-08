---
title: "Contribution Guidelines"
linkTitle: "Contribution Guidelines"
weight: 100
description: >
    How to contribute to the docs
---

We use:
- [Hugo](https://gohugo.io/) to format and generate our website,
- the [Docsy](https://github.com/google/docsy) theme for styling and site structure,
- [Netlify](https://github.com/YCloudYUSA/yusaopeny_docs/blob/main/netlify.toml) for PR previews, and
- [GitHub Actions](https://github.com/YCloudYUSA/yusaopeny_docs/blob/main/.github/workflows/gh-pages.yml) to manage the deployment of the site to GitHub Pages.

Hugo is an open-source static site generator that provides us with templates,
content organisation in a standard directory structure, and a website generation
engine. You write the pages in Markdown (or HTML if you want), and Hugo wraps them up into a website.

All submissions, including submissions by project members, require review. We
use GitHub pull requests for this purpose. Consult
[GitHub Help](https://help.github.com/articles/about-pull-requests/) for more
information on using pull requests.

## Updating a single page

If you've just spotted something you'd like to change while using the docs, Docsy has a shortcut for you:

1. Click **Edit this page** in the right (second) sidebar.
2. If you don't already have an up-to-date fork of the project repo, you are prompted to get one - click **Fork this repository and propose changes** or **Update your Fork** to get an up-to-date version of the project to edit. The appropriate page in your fork is displayed in edit mode.
3. Make your changes and open a Pull Request. The maintainers will review, provide feedback, and merge.

## Previewing your changes locally

If you want to run your own local Hugo server to preview your changes as you work:

1. Follow the instructions in [Getting started](https://www.docsy.dev/docs/getting-started/) to install Hugo and any other tools you need.
2. Fork the [yusaopeny_docs](https://github.com/YCloudYUSA/yusaopeny_docs) repo into your own project, then create a local copy using `git clone`.
3. Run `hugo server` in the site root directory. By default, your site will be available at `http://localhost:1313/`. Now that you're serving your site locally, Hugo will watch for changes to the content and automatically refresh your site.
4. Continue with the usual GitHub workflow to edit files, commit them, push the
   changes up to your fork, and create a pull request.

### Common options

Hugo has [a number of flags](https://gohugo.io/commands/hugo_server/#options) you can use to change local server behavior, here are a few we like:

- `--tlsAuto` generate and use locally-trusted certificates to run the site over `https`
- `--buildDrafts` include content marked as draft
- `--buildFuture` include content with publishdate in the future

With all of these, you might end up with something like:

```shell
hugo serve --tlsAuto --buildDrafts --buildFuture
```

## Creating an issue

If you've found a problem in the docs, but you're not sure how to fix it yourself, please create an issue in the [yusaopeny_docs repo](https://github.com/YCloudYUSA/yusaopeny_docs/issues). You can also create an issue about a specific page by clicking the **Create Issue** button in the top right hand corner of the page.

## Useful resources

* [Docsy user guide](https://www.docsy.dev/docs/): All about Docsy, including how it manages navigation, look and feel, and multi-language support.
* [Hugo documentation](https://gohugo.io/documentation/): Comprehensive reference for Hugo.
* [GitHub Hello World!](https://guides.github.com/activities/hello-world/): A basic introduction to GitHub concepts and workflow.
