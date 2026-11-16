# Virtual Cog

A phone web app that gives a Tacx smart trainer **virtual shifting**, like a single-speed
"cog" setup: leave the chain in one real gear and shift through 24 virtual gears on your phone.

Open `https://<your-pages-site>/cog/` in **Chrome on Android** (or the **Bluefy** browser on iPhone;
Safari has no Web Bluetooth). Tap *Add to Home screen* for a full-screen app.

## How it works
- Connects to the trainer over Bluetooth, preferring Tacx **FE-C over BLE** and falling back to **FTMS**.
- Every 250 ms it works out the force you'd push in the chosen virtual gear on the chosen road grade
  (using rider + bike weight, CdA and Crr), then scales it by *virtual ratio / real ratio* so the
  pedal torque matches the virtual gear.
- **SIM mode** (default) sends that as a slope with air drag turned off, so the trainer reacts instantly.
  **ERG mode** sends the exact wattage instead.

## Setup
1. Put the chain in one gear on the trainer (e.g. 34×17) and enter it in Settings,
   or pedal at 60+ rpm and tap **Detect gear**.
2. Set rider/bike weight. Use **Feel** to make everything lighter or heavier.
3. Shift with the big buttons (hold to repeat) or a Bluetooth keyboard/remote
   (↑ → PageDown + for harder, ↓ ← PageUp − for easier).

## Limits
- While the phone controls the trainer, other apps (e.g. Zwift) can't also control it.
  You can still pair the trainer in another app as a **power/cadence source only**, if it accepts a
  second connection (e.g. ANT+), but you'll feel this app's grade, not the game's.
- Most Tacx trainers cap the slope at about +20–25%, and only motorised models (Neo) can push you downhill.
