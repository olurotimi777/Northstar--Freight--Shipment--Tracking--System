# Northstar Freight — Static Shipment Tracking Demo

A polished, responsive, **fictional** logistics tracking website using only HTML, CSS, JavaScript and JSON. No backend, external tracking API, login, or database is needed.

## Files

- `index.html` — marketing homepage and tracking search
- `tracking.html` — shipment lookup, details, timeline, route progress, print / Save as PDF
- `admin.html` — **insecure demo-only** browser-local records management
- `style.css` — responsive layout and components
- `script.js` — lookup, local storage, timeline and admin functions; includes a sample-data fallback for local file previews
- `shipments.json` — canonical fictional sample database (10 shipments)

## Quick start

**Option A — Simply open `index.html` in your browser.** The included embedded sample fallback allows tracking even when browser restrictions block fetching JSON through `file://`.

**Option B — Recommended local server:**

```sh
cd shipment-tracking-site
python -m http.server 8000
```

Visit http://localhost:8000 . This loads `shipments.json` normally.

## Sample tracking numbers

- `SHP2026001234` — In Transit
- `SHP2026005678` — Delivered
- `SHP2026009012` — Customs Clearance
- `SHP2026001122` — Shipment Created
- `SHP2026002233` — Package Picked Up
- `SHP2026003344` — Arrived at Sorting Facility
- `SHP2026004455` — Out for Delivery
- `SHP2026005566` — Delivery Exception
- `SHP2026006677` — In Transit
- `SHP2026007788` — Delivered

## Demo admin

Open `admin.html` to add, search, edit, delete, and reset shipment records. You can create dated history events, adjust statuses, and save changes. **Changes are stored only in your current browser** using Local Storage and won't appear to other users or on other devices. The editor has no authentication or server-side permission controls, so **never use it for real shipment administration or sensitive data**. Other visitors see the original JSON-based sample records. Reset Demo Data restores the original 10 samples.

The current status must have a corresponding recorded history event. Delivered status also requires an actual delivery date.

## Printing and PDF

From the tracking results, select **Print** to print the details. Select **Save as PDF** to open the browser's print dialog, then choose **Save as PDF** as your print destination. This is the native browser PDF workflow (no external PDF library). The demo does not silently download a generated PDF.

## Deploy

### Netlify
Drag the contents of the `shipment-tracking-site` folder into Netlify's deployment interface, or connect a Git repository with this folder as the publish directory. No build command.

### Vercel
Import the Git repository as an **Other** / static site and configure the root/publish directory appropriately. No server code is required.

### GitHub Pages
Push these files to a repository, then enable Pages under **Settings → Pages**, deploying from the chosen branch and root folder. All pages use relative links and work under a repository subpath.

## Important limitations

- All names, shipments, statuses, dates, locations, and tracking events are **fictional demo data**. No live courier updates, map/GPS position, actual services, or guaranteed ETAs are provided.
- The route progress bar represents recorded **milestones**, not actual geographic distance or live location.
- Font styling optionally loads Google Fonts; system font fallbacks and core functionality continue to work offline.
- Browsers can restrict Local Storage under local file URLs or privacy modes; use a local server if local edits aren't retained.
- Tracking lookup sanitizes tracking IDs and the UI escapes HTML when rendering records; this is not a substitute for backend authorization for a real-world system.
- For production, replace this static design with authenticated server-side storage and integrations; never put personal customer data into a public JSON file.

## Customize

Edit `shipments.json` to change the shipped demo dataset. Because `script.js` includes the same sample records as a `file://` fallback, update the `EMBEDDED_SAMPLES` constant as well if you want double-click/offline previews to reflect new examples. Existing browser-local admin edits override the samples until **Reset Demo Data** is used or Local Storage is cleared.

# Northstar--Freight--Shipment--Tracking--System
