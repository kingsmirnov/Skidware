# Skidware

Skidware is a security creator workspace with account sign-up and sign-in, profile editing and picture uploads, project listings, and a contact-based marketplace.

## Preview locally

Open `index.html` in a browser. Local preview stores accounts and listings in that browser. Shared accounts and listings require the Cloudflare deployment below.

## Deploy with Cloudflare dashboard (no Wrangler)

1. In Cloudflare, open **Workers & Pages** and create a Pages project with **Direct Upload / Drag and drop**.
2. Upload this `Skidware` folder and deploy the site. The `_worker.js` file serves the site assets and handles the `/api/` routes.
3. In Cloudflare, create a D1 database.
4. In the Pages project's settings, add a D1 database binding named `DB`, select the database, then redeploy.
5. Visit the Pages URL. The Worker creates its database tables when the API is first used.

Cloudflare supports dashboard drag-and-drop Pages deployments with `_worker.js`: [Direct Upload documentation](https://developers.cloudflare.com/pages/get-started/direct-upload/). See [Advanced Mode](https://developers.cloudflare.com/pages/functions/advanced-mode/) for how the Worker serves static assets.

## Files

- `index.html` — website structure
- `styles.css` — visual design
- `app.js` — website interactions and API calls
- `_worker.js` — Cloudflare Pages Worker API and static asset handler
