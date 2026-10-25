# PAC-MAN AR — Reliable rebuild

A dependency-free browser project. The actual mini-game and rendering code are local HTML/JavaScript; there are no external scripts or CDN libraries.

## Files
- `index.html` — playable 2D game and camera/QR AR mode.
- `poster.html` — full-screen laptop target page.
- `pacman-poster.png` — poster with the exact QR payload `PACMAN-AR-POSTER-V2`.
- `TARGET-CODE.txt` — target string used by the scanner.

## Publish from a clean repository
1. Extract this ZIP.
2. Create a **public** GitHub repository.
3. Upload the files inside this folder directly to the repository root (do not upload the ZIP itself and do not nest them in another folder).
4. In **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/(root)`, and save.
5. Wait until GitHub Pages shows the site as published.

## Test in this order
1. Phone: open `https://YOUR-USERNAME.github.io/YOUR-REPO/` in current Chrome for Android.
2. Tap **PLAY 2D TEST MODE**. Tap an arrow or use WASD/arrow keys. Pac-Man should move and pellets/score should change.
3. Laptop: open `https://YOUR-USERNAME.github.io/YOUR-REPO/poster.html` and keep the full QR code visible.
4. Phone: return to the homepage, tap **START CAMERA AR**, allow camera access and aim at the QR code near the top of the poster.
5. The status should say `TARGET LOCKED`. The overlay maze appears in the poster's lower game zone so the QR target stays visible and tracking can continue.

## Compatibility notes
- Camera requires HTTPS and browser camera permission.
- AR detection uses the browser's built-in `BarcodeDetector` API with `qr_code` support; current Chrome for Android is the intended browser. This browser API is not available in every browser/device.
- The project is self-contained; if QR detection is unsupported, the 2D game still works and the page displays a visible error instead of freezing.
- This is an original mini-game inspired by maze-chase gameplay, not the original commercial Pac-Man ROM.
