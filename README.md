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
- **Snapshot** — opens the iOS share sheet; choose *Save to Photos*.
- **Full** — fullscreen; tap the image to hide/show the controls.

The screen is kept awake while viewing.

## Notes

- Everything runs locally in the browser. No network requests, no uploads.
- Settings (camera, rotation, adjustments) are stored in the browser only.
- Tested with a cheap generic 640×480 UVC endoscope on an iPad Pro (M1).

## License

MIT — see [LICENSE](LICENSE).
