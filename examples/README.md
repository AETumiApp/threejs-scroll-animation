# threejs-scroll-animation — Examples

Scroll-driven Three.js (r160) animation. No build step: open the `.html` file in a modern browser and scroll.

| Example | Description |
| --- | --- |
| [`scroll-scene.html`](./scroll-scene.html) | A scroll-scrubbed 3D scene: normalized scroll position (0→1) drives camera dolly, object rotation, and a color/background shift on a single deterministic timeline. The canvas is pinned with `position: sticky`. Not autoplay — the scene only moves when you scroll. |

Includes a `prefers-reduced-motion` fallback that shows a single static frame with no scroll coupling. Handles resize.

Explore more on the hub: **https://aetumi.app** · scroll experiences → https://aetumi.app/etec

---

## Example backlog / roadmap

# Three.js Scroll Animation Example Backlog

## Planned examples

### Pinned camera story

Map semantic HTML chapters to deterministic camera positions while a Three.js canvas remains pinned.

### Product exploded view

Drive part separation from normalized scroll progress and provide a reduced-motion fallback.

### Scroll-linked material transition

Blend material properties or lighting states without performing heavy work inside the scroll handler.

### Mobile fallback

Show how the same narrative can remain useful when the full pinned 3D experience is disabled on smaller or constrained devices.

### Performance instrumentation

Document frame time, visibility pausing and asset-loading behavior for a scroll-driven scene.

## Quality bar

Every example should include:

- normalized progress model
- one render loop
- resize behavior
- mobile behavior
- reduced-motion fallback
- semantic narrative content outside canvas

## AETumi links

- https://aetumi.app/3d-scroll/
- https://aetumi.app/threejs/
- https://aetumi.app/interactive-websites/
