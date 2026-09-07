# threejs-scroll-animation — Examples

Scroll-driven, **production-grade** Three.js (r160) animation. No build step: open the `.html` file in a modern browser and scroll.

| Example | Description |
| --- | --- |
| [`scroll-scene.html`](./scroll-scene.html) | A scroll-scrubbed 3D scene: normalized scroll position (0→1) drives camera dolly, object rotation, and a color/background shift on a single deterministic timeline. The canvas is pinned with `position: sticky`. Not autoplay — the scene only moves when you scroll. |

### Expert / production features (every example)

- **Capability detection + graceful fallback** — probes WebGL2 → WebGL → none. With no WebGL context it paints a tasteful CSS gradient poster instead of a blank canvas; low-power devices start at reduced quality.
- **Adaptive performance** — DPR capped at 2; rendering is scroll-driven and coalesced through `requestAnimationFrame`, never an idle loop. A rolling FPS average steps DPR and the depth-field point count down below 50 fps and back up above 58 fps with hysteresis, and work is skipped while the sticky stage is offscreen (`IntersectionObserver`) or the tab is hidden.
- **Strict cleanup** — one teardown on `pagehide` removes scroll/resize listeners and disposes all geometries, materials and the renderer.
- **Accessibility** — the canvas is `role="img"` with an `aria-label`; captions are real page text; `prefers-reduced-motion` renders one representative static frame with **no** scroll coupling.
- **Premium look** — ACES Filmic tone mapping, key + rose rim lighting, and a cobalt→rose color/fog shift across the timeline.

Three.js r160 is loaded as ES modules through an importmap on **jsDelivr only** (`three` + `three/addons/`).

Explore more on the hub: **https://aetumi.app** · scroll experiences → https://aetumi.app/etec
