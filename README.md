# Hand Particle Saturn — ready-to-deploy

Simple web demo that forms a 3D Saturn made of particles when the user makes a fist, disperses particles on open palm, and writes text on two-finger gesture. Works on mobile and desktop. Uses Three.js and MediaPipe Hands.

## Files
- `index.html` - main page with start button and controls
- `app.js` - main logic, performance adaptation, MediaPipe integration
- `.gitignore` - common ignores

## How to run (quick)
1. Clone repo.
2. Serve via HTTPS or localhost. Examples:
   - Locally: `python -m http.server 8000` then open `http://localhost:8000` on the same machine
   - Quick public test: `ngrok http 8000` then open the https url on your phone
   - Deploy: GitHub Pages, Vercel, Netlify will provide HTTPS automatically

## Important notes for mobile
- Must be served over HTTPS to access camera on mobile browsers.
- Tap the "Tap to start camera" button first. This makes sure iOS allows the camera stream.
- If performance is choppy, try lowering particle count via `TOTAL` in `app.js` or reduce browser tab load.

## Tuning
- Change default text via URL parameter: `?text=HELLO`
- Edit `TOTAL` value in `app.js` for more/fewer particles
- Try reducing `renderer.setPixelRatio` multiplier for lower GPU load on low-end phones

## Debugging
- Use Chrome remote debugging or Safari Web Inspector for mobile console logs
- If camera permission denied, enable it in browser settings