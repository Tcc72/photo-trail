# Photo trail

Pin your photos on a satellite map in the order you took them.

## Put it online (about 2 minutes, free)

The app needs to be served over https so the camera, location and
"Add to Home Screen" install work. Any static host will do.

**Netlify Drop (easiest, needs a computer):**
1. Unzip this folder.
2. Go to https://app.netlify.com/drop and drag the folder onto the page.
3. You get a link like `https://something.netlify.app`. Sign up (free) to keep it
   and rename it.

**GitHub Pages:**
1. Create a new public repository and upload all the files in this folder.
2. Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Your app appears at `https://<username>.github.io/<repo>/` within a minute.

## Install it on your phone

- **iPhone (Safari):** open the link → Share → Add to Home Screen.
- **Android (Chrome):** open the link → menu ⋮ → Install app.

It then opens full-screen from its own icon, like any other app.
Allow location when asked the first time you tap **Take photo**.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | App name, colours and icons for installing |
| `sw.js` | Lets it open offline and load quickly |
| `icon.svg`, `icon-*.png`, `apple-touch-icon.png`, `favicon.png` | Logo at each size |

## Notes

- Trails are saved on the phone itself (in the browser's storage). Nothing is
  uploaded anywhere. Deleting the app or clearing site data removes them.
- Satellite imagery: Esri World Imagery, free for light use with the credit shown
  on the map. For a public launch with heavy traffic, check Esri's terms or switch
  to a keyed provider such as Mapbox or MapTiler.
- After changing files, bump `CACHE` in `sw.js` (e.g. `photo-trail-v2`) so
  installed copies pick up the update.
