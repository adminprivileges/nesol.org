# NE Solutions Website

This repository contains the source code for the NE Solutions website.

The site is built with open source tools and deployed as a static website using GitHub Pages. It was created to showcase a more maintainable and professional alternative for website building and hosting while keeping the workflow simple enough for regular content updates.

## Technology Used

This site uses:

- [Hugo](https://gohugo.io/) as the static site generator
- [Tella](https://github.com/opera7133/tella) as the Hugo theme
- [Tailwind CSS](https://tailwindcss.com/) for styling through the theme
- [GitHub Pages](https://pages.github.com/) for hosting
- [GitHub Actions](https://github.com/features/actions) for automated builds and deployment
- [Cloudflare](https://www.cloudflare.com/) for DNS management

Because this is a static site, there is no server-side application, database, or content management system required. Pages are written as Markdown files and then built into static HTML, CSS, and JavaScript.

## Repository Structure

```text
.
├── content/                 # Site pages and written content
│   ├── _index.md             # Homepage content
│   ├── about.md              # About page
│   ├── contact.md            # Contact page
│   ├── skillbridge.md        # SkillBridge page
│   └── careers/              # Career listing pages
├── data/                     # Homepage carousel and feature block data
├── layouts/                  # Local theme overrides
├── static/                   # Static files such as images, favicon, and custom CSS
├── themes/tella/             # Tella Hugo theme, added as a Git submodule
├── hugo.toml                 # Main Hugo configuration
├── package.json              # Node/Tailwind dependencies
└── .github/workflows/        # GitHub Actions deployment workflow
```

## Getting Started

To work on the site locally, first clone the repository:

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
```

Because the theme is included as a Git submodule, initialize submodules after cloning:

```bash
git submodule update --init --recursive
```

Install the Node dependencies:

```bash
npm install
```

Then run the Hugo development server:

```bash
hugo server -D
```

The site should be available locally at:

```text
http://localhost:1313/
```

The `-D` flag includes draft pages while previewing the site.

## Editing Content

Most site content is stored in the `content/` directory.

For example:

```text
content/about.md
content/contact.md
content/skillbridge.md
content/careers/software-engineer.md
```

Each page has front matter at the top, followed by Markdown content:

```toml
+++
title = "Software Engineer"
date = 2026-05-24T00:00:00-04:00
draft = false
image = "img/careers/software-engineer.jpg"
+++
```

To publish a page, make sure:

```toml
draft = false
```

To keep a page hidden from production builds, use:

```toml
draft = true
```

## Homepage Data

The homepage carousel is controlled by:

```text
data/slide.json
```

The homepage feature blocks are controlled by:

```text
data/features.json
```

Images referenced in those files should be placed under `static/`.

For example, this image file:

```text
static/img/slide/home-hero.jpg
```

is referenced in data files as:

```text
img/slide/home-hero.jpg
```

Do not include `static/` in the image path.

## Career Pages

Career postings are stored under:

```text
content/careers/
```

Each career page can include an image for homepage/card previews:

```toml
image = "img/careers/example.jpg"
```

The matching image should be stored in:

```text
static/img/careers/example.jpg
```

## Custom Styling

Site-specific styling can be added in:

```text
static/css/custom.css
```

Some theme-level colors are controlled through Tailwind-related CSS in:

```text
assets/css/style.css
```

Local layout overrides are stored in:

```text
layouts/
```

These files override the matching files from the Tella theme without editing the theme directly.

## Deployment

This site is deployed using GitHub Pages and GitHub Actions.

The deployment workflow is stored in:

```text
.github/workflows/hugo.yaml
```

When changes are pushed to the `main` branch, GitHub Actions builds the Hugo site and deploys the generated static files to GitHub Pages.

A normal update workflow looks like this:

```bash
hugo server -D
git status
git add .
git commit -m "Update site content"
git push origin main
```

After pushing, check the repository’s **Actions** tab on GitHub to confirm the deployment succeeded.

## DNS and Hosting

The site is hosted through GitHub Pages.

DNS is managed through Cloudflare. The production domain points to GitHub Pages using the DNS records recommended by GitHub.

The intended production URL is:

```text
https://www.nesol.org/
```

## Open Source Approach

This site is built using open source technology so that the project is portable, transparent, and maintainable. Hugo generates the site from plain text files, the Tella theme provides the visual foundation, and GitHub Pages hosts the final static site without requiring a custom server.

This approach is useful for small business, nonprofit, personal, and project websites that do not need a full database-backed content management system.

To build a similar site:

1. Create a Hugo site.
2. Choose a Hugo theme.
3. Write pages in Markdown.
4. Preview the site locally with `hugo server`.
5. Push the source code to GitHub.
6. Use GitHub Actions to build and deploy the site.
7. Point a custom domain to GitHub Pages.

## License

The website content, and branding belong to NE Solutions unless otherwise noted.

All images are free use images. Please [Contact Us](https://www.nesol.org/contact/) for any inquiries or disputes for image use.

The site uses third-party open source software and theme components under their respective licenses. Check the linked projects for their license details.