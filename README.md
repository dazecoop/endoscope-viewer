# Endoscope Viewer

A single-page web app for viewing a USB (UVC) endoscope or microscope camera on
an **iPad** through Safari — no App Store app, no developer account.

iPhones can't use external USB cameras at all (iOS blocks UVC devices system-wide,
so every "USB camera" app fails). An **iPad with a USB-C port** (iPadOS 17+) can,
in apps *and* in Safari. This page is just a nice front-end over that: plug the
scope into the iPad, open the page, pick the camera.

## Use it

1. Host the folder over **HTTPS** — Safari only grants camera access on a secure
   origin. GitHub Pages, Netlify, Cloudflare Pages, etc. all work. (A plain
   `file://` won't get the camera.)
2. On the iPad, plug the endoscope into the USB-C port.
3. Open the hosted URL in Safari and tap **Start camera**, then allow access.
4. If the wrong camera shows, pick the scope from the dropdown (usually
   "HD camera" rather than "Front/Back Camera"). Your choice is remembered.

Tip: **Share → Add to Home Screen** to launch it fullscreen like an app.

## Controls

- **Rotate / Mirror** — endoscope feeds are usually sideways or flipped.
- **Adjust** — brightness, contrast and saturation, useful in dark cavities.
- **Snapshot** — captures instantly into the in-app gallery with a screen
  flash and a beep. No dialog, so it works hands-free from an awkward spot.
- **Gallery** — review your captures, then **Save all to Photos** in one step,
  or open a shot to save or delete it individually.

The screen is kept awake while viewing.

### Saving to Photos

iOS does not allow a web app to write to the Photos library silently — the
share sheet (or long-pressing an image) is the only route Apple permits. So
captures collect in the app's own gallery as you work, and you push them to
Photos in a single batch afterwards, when you can comfortably reach the iPad.
The gallery is stored locally (IndexedDB) and survives reloads.

### Hardware shutter

The button on many endoscope cables only triggers the camera's internal UVC
capture, which browsers can't see — so it won't work here. A cheap **Bluetooth
camera-shutter remote or footswitch** set to Android/keyboard mode pairs as a
keyboard, and any key it sends fires the shutter. (Any paired keyboard key does,
while the app is open.)

## Notes

- Everything runs locally in the browser. No network requests, no uploads.
- Settings (camera, rotation, adjustments) are stored in the browser only.
- Tested with a cheap generic 640×480 UVC endoscope on an iPad Pro (M1).

## License

MIT — see [LICENSE](LICENSE).
