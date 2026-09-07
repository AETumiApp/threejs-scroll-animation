# Three.js Scroll Animation with AETumi

A production-focused guide to building **scroll-driven 3D websites with Three.js, WebGL, React and Next.js**.

**AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, 3D scenes, AI prompts, and MCP workflows for AI coding assistants.**

## Why scroll-driven 3D needs structure

Scroll storytelling can create strong product and brand experiences, but it also combines browser scrolling, rendering loops, animation state and responsive layout. Without a clear model, the result becomes fragile very quickly.

This repository focuses on patterns for:

- camera motion tied to normalized scroll progress
- pinned storytelling sections
- product reveal and exploded-view sequences
- parallax depth
- scene transitions
- material and lighting changes
- narrative product pages
- progressive enhancement for devices that should not run the full 3D experience

## Recommended state model

Treat scroll as input, not as the animation engine itself.

```text
scroll position
    ↓
normalized progress 0..1
    ↓
scene state / timeline
    ↓
render frame
```

This keeps behavior deterministic and easier to test across viewport sizes.

## Production checklist

- use one authoritative animation loop
- avoid doing heavy work directly inside scroll events
- clamp and normalize progress
- test browser resize and mobile address-bar changes
- design a touch-friendly fallback
- respect `prefers-reduced-motion`
- pause rendering when the experience is not visible where practical
- lazy-load models and high-resolution textures
- keep narrative headings and copy in semantic HTML
- profile main-thread and GPU cost on mid-range phones

## Common patterns

### Product reveal

A product moves from distant framing into detail as sections explain features.

### Exploded assembly

Parts separate along controlled paths, then return to an assembled state.

### Camera chapter system

Each content chapter maps to a camera position, target and scene state.

### Scrollytelling backdrop

The 3D layer remains pinned while semantic HTML chapters move over or beside it.

## AETumi resources

- [3D Scroll](https://aetumi.app/3d-scroll/)
- [Three.js](https://aetumi.app/threejs/)
- [3D Websites](https://aetumi.app/3d-websites/)
- [Interactive Websites](https://aetumi.app/interactive-websites/)
- [3D Components](https://aetumi.app/3d-components/)
- [Docs](https://aetumi.app/docs/)

## Related repositories

- [threejs-product-viewer](https://github.com/AETumiApp/threejs-product-viewer)
- [nextjs-threejs-starter](https://github.com/AETumiApp/nextjs-threejs-starter)
- [claude-code-threejs](https://github.com/AETumiApp/claude-code-threejs)
- [aetumi-3d-web-examples](https://github.com/AETumiApp/aetumi-3d-web-examples)

## Repository status

Active. Runnable, production-oriented examples now live in [`examples/`](./examples/) — reviewed for performance (adaptive quality), accessibility, reduced-motion and non-WebGL fallbacks, and clean resource disposal. The set is refined and extended as new patterns land.

See [examples/README.md](./examples/README.md).
## About AETumi

AETumi helps designers, developers and agencies create cinematic 3D web experiences with Three.js, WebGL, Next.js, React, React Three Fiber, MCP and AI coding assistants.

Main site: https://aetumi.app/