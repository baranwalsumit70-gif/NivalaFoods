# Nivala Foods

Premium Indian rice brand website — Home, Shop, Product Detail, About, Our Farms, Rice Guide, Contact, plus a working cart drawer and secure checkout flow.

## Run it

Any static server works. From the repo root:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/index.html`.

## Files

- `index.html` — the complete site in one file. Fonts, scripts and **all photography are embedded**. Upload this file on its own and it works.
- `Nivala Foods.dc.html` — the source design. Edit this, not `index.html`.
- `support.js` — runtime required by the source file.
- `image-slot.js` — drag-and-drop image placeholder component.
- `assets/nivala-logo.png` — brand logo.
- `assets/` — original source images (pack renders, lifestyle, journey). Used when rebuilding; not needed at runtime.
- `nivala-images.js` — the images encoded for embedding. Regenerate if you change anything in `assets/`.

## Deploying to GitHub Pages

1. Push this repo to GitHub. `index.html` is self-contained, so it works even if uploaded alone.
2. Settings → Pages → Source: `main` branch, root folder.
3. The site serves over HTTPS at `https://<user>.github.io/<repo>/`.

## Photography

Source photos live in `assets/`. They are baked into `index.html` at build time, so replacing a file means rebuilding the page for the change to appear.

Slots still empty show a caption describing the shot they need. Drag a photo onto one in the browser to preview it — but a browser drop only saves locally. To make it permanent, save the image into `assets/slots/` under that slot's id and add the id to the `SLOT_IMAGES` list in `Nivala Foods.dc.html`.

## Notes on security

Checkout shows the visible trust layer: encrypted-connection badge, masked card entry, PCI/UPI badges, privacy copy. Real payment processing and data encryption require a server and a payment gateway; this is a front-end build only.

## Stack

No build step, no dependencies. Playfair Display + DM Sans from Google Fonts.
