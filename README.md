# Tabata Projects website

Practical Engineering. Reliable Infrastructure.

Static website for Tabata Projects (Pty) Ltd, built for **GitHub Pages**.
One `index.html`, one `images/` folder. No build step, no dependencies.

## Pages

The site is a single HTML file with client-side page switching:

| Page | URL hash |
|---|---|
| Home | `index.html#/home` |
| About Us | `index.html#/about` |
| Services | `index.html#/services` |
| Project Experience | `index.html#/projects` |
| Service Areas | `index.html#/areas` |
| Company Information | `index.html#/company` |
| Contact Us | `index.html#/contact` |

The hamburger button (three horizontal lines) opens the menu on mobile and
closes again when a page is chosen. Direct links to a page (for example
`www.tabataprojects.co.za/#/projects`) land on that page, so you can share
deep links anywhere.

## Publish on GitHub Pages

1. Create a repository on GitHub (for example `tabata-website`).
2. Upload these files and folders to the repository
   (`index.html`, `CNAME`, `README.md`, `.nojekyll`, and the whole `images/` folder).
3. Go to **Settings > Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**,
   branch **main**, folder **/ (root)**, and save.

The site is then served at the address below.

## Using your own domain (www.tabataprojects.co.za)

The `CNAME` file in this repo already contains `www.tabataprojects.co.za`,
so GitHub Pages serves the site on that address once DNS points here:

- At your DNS provider, add a **CNAME record** for the host `www` pointing to
  `<your-github-username>.github.io` (for example `akho.github.io`).
- In **Settings > Pages**, under **Custom domain**, enter
  `www.tabataprojects.co.za` and save. Wait for the DNS check to pass.
- To also cover the bare domain (without www), add the four GitHub A records
  at the root, per GitHub's documentation:
  185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
- When the DNS check passes, tick **Enforce HTTPS**.

If you prefer to use the free `github.io` address instead, delete the `CNAME`
file before uploading, and the site will publish at
`<your-github-username>.github.io/<repository-name>`.

## Editing content

All text lives in `index.html`. Each page is a `<section class="page" id="page-...">`
block. Photos of real projects can replace the illustration files in `images/`
by keeping the same file names, or by updating the `src` paths.

## Files

- `index.html` — the whole site (pages, styling and switching script).
- `images/` — illustrations (generated for this site, not photographs).
- `CNAME` — custom domain for GitHub Pages.
- `.nojekyll` — tells GitHub Pages to serve files as-is.
