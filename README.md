# Grand Atlas — React Frontend

Real estate frontend based on the supplied project assets, using **React 19**, **Vite**, **Tailwind CSS 4**, and React Router. Pages: home, property listings & details, zones & details, developers & details, and contact.

## Start locally

1. Install Node.js 20.19+ (or 22.12+).
2. Run `npm ci` in this folder.
3. Run `npm run dev` and open http://localhost:3000.
4. Production test: `npm run build` then `npm run preview`.

The site sends requests to `/api/v1/...`. Vite proxies these requests during development, and `vercel.json` rewrites them to the supplied backend in production. If needed, set `VITE_API_BASE_URL` to an alternative public backend URL (be aware of CORS for cross-origin URLs).

## Deploy with GitHub + Vercel

1. Create a new GitHub repository and upload this project's **contents** (not the zip itself). `node_modules` and `dist` should not be committed.
2. In Vercel select **Add New → Project → Import Git Repository**.
3. Framework: **Vite**. Build command: `npm run build`. Output directory: `dist`. Install command: `npm ci`.
4. Click **Deploy**. `vercel.json` handles SPA deep links and the `/api` proxy.

## Notes and verification status

- The provided ZIP already contained the design and page structure; this edition improves API routing, API response handling, mobile layouts, loading/error states, and detail pages.
- The Figma canvas was not available to inspect automatically, so pixel-identical fidelity to the linked Figma cannot be guaranteed.
- The backend Swagger UI was not readable in this environment. Existing endpoints `/unit`, `/zone`, `/developer` were retained from the provided code; validate payload shapes and the API proxy in a deployed browser.
- The contact form uses a `mailto:` fallback to prefill an email message. No contact POST endpoint was verified; replace this fallback with the documented API endpoint if available.

## Asset integration changes (this revision)

- Original `src/assets/Logo.svg` confirmed to contain the Grand Atlas branded emblem and wordmark. Navbar and footer display the real logo with controlled sizes; also copied to `public/Grand-Atlas-Logo.svg`. No replacement logo was fabricated.
- Preserved supplied hero photography, About image, milestone icons, gallery, location image, future development imagery and developer brand badges.
- Added existing supplied fallback imagery (`Card.png`, `Zones1.png`, `Future1.png`) for API records missing images, and corrected absolute backend `/uploads/`, `/storage/`, `/media/` image paths.
- Replaced the inherited Lift Media footer template and unrelated support details with Grand Atlas information already present on the contact page.
- Made header Contact Us, hero Explore, About Know More, and showcase tile links navigate to actual app routes.
- Brought mobile/desktop navbar logo into consistent sizing and kept social icons inside the hero.
- Missing data from the live backend is **not** invented; API connection, live images, and pixel-for-pixel Figma fidelity require final browser/backend verification.
