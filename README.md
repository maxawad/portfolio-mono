# Luis Mono Photography Portfolio

A small, three-page photography portfolio website with a photo gallery, an about page and a contact page. It is a re-skin of an open source photographer template, customised with the name "Luis Mono" and links to the Redxam Network and an Instagram profile.

![Screenshot of the portfolio](dist/assets/mockup.png)

## What it does

- Home page with a masonry-style photo gallery. Clicking a photo opens it full size in a lightbox (Fancybox).
- About page with an avatar and short bio.
- Contact page with a simple form that opens the visitor's email program (`mailto:`).
- Light and dark mode that follows the visitor's system setting.
- Responsive layout with a hamburger menu on small screens and a fade-in on load.

## Tech stack

- HTML and JavaScript, no build framework
- Tailwind CSS (loaded from the Tailwind CDN on the home page, and a prebuilt `dist/output.css` on the other pages)
- Alpine.js, Fancybox and jQuery, all loaded from CDNs
- Google Fonts (Signika, Nothing You Could Do)
- Gallery photos from Unsplash

## Run it

There is nothing to install. It is a static site, so any static file server works. From the repository root:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000/ in a browser. Opening `index.html` directly from the disk also works for most things.

The browser needs internet access, because the scripts, fonts and photos are loaded from CDNs.

### Optional: rebuild the Tailwind CSS

`dist/output.css` is already built and committed. If you want to regenerate it after editing the HTML, you need a `tailwind.config.js` that lists the HTML files in `content` (the original one is not in this repository), then run:

```sh
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

### Host it as a live demo

The whole repository is static files with no secrets, so it can be served as is, for example with GitHub Pages or Netlify. No build step is needed. Publish the repository root (the folder that contains `index.html`).

## Project layout

- `index.html`: home page and gallery
- `dist/about_me.html`, `dist/contact.html`: the other two pages
- `dist/output.css`: prebuilt Tailwind CSS used by the other two pages
- `dist/fade_in.js`, `dist/menu.js`: page fade-in and mobile menu
- `dist/assets/`: logo, favicon, avatar and the screenshot
- `src/input.css`: Tailwind entry file with a few custom utilities

## Status

Working, but a template-level prototype. Things to know:

- The home page loads five photos from `source.unsplash.com`, an Unsplash service that has been shut down, so those images may not load. Replace them with your own photos or direct `images.unsplash.com` links.
- The contact form sends nothing to a server. It opens a `mailto:` link to the placeholder address `info@example.com`, and the contact page heading still says "Sophia Williams" from the original template. Update these before using the site for real.
- The Facebook, Twitter, LinkedIn and Behance links point to the sites' home pages.

## Credits

This project is based on the open source [photography-portfolio](https://github.com/JoaoFranco03/photography-portfolio) template by João Franco, with changes by Max Awad (Redxam Network). Thanks also to [Tailwind CSS](https://tailwindcss.com), [Alpine.js](https://alpinejs.dev), [Fancybox](https://fancyapps.com/fancybox/) and [Unsplash](https://unsplash.com/) photographers.

## License

MIT, see [LICENSE](LICENSE).
