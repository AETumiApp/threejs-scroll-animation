# Three.js Scroll Animation: Production Guide

Scroll-driven 3D can turn a website into a strong narrative experience when the motion reveals information in a deliberate sequence. It can also turn into a nausea-powered benchmark if every scroll tick launches five effects. This guide keeps the useful part.

AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, interactive 3D scenes, AI prompts and MCP workflows.

## Good use cases

- product assembly and exploded views
- camera fly-throughs
- feature reveals
- automotive storytelling
- luxury product launches
- architecture walkthroughs
- pinned 3D hero narratives
- transition from product exterior to internal layers

## Architecture model

Treat scroll position as an input signal rather than allowing multiple animation systems to fight over scene state.

A predictable model is:

```text
scroll progress → normalized timeline → camera/object/material state
```

This makes the scene easier to test, scrub and adapt to mobile fallbacks.

## Normalize progress

For a section with a known scroll range, map the section's visible progress to a 0–1 value. Then derive scene states from that number.

Conceptually:

```js
progress = clamp((scrollY - start) / (end - start), 0, 1)
```

From there, interpolate camera position, model rotation, exploded offsets or shader uniforms.

## Avoid event-driven chaos

Do not create a new animation every time the user crosses a tiny threshold. Prefer deterministic state derived from progress. This avoids desynchronization when users scroll quickly, reverse direction or resize the page.

## Pinned storytelling

A common pattern is a tall semantic section with a sticky canvas and normal HTML narrative content.

Advantages:

- content remains crawlable
- headings and copy remain accessible
- 3D can stay visually persistent while text changes
- mobile fallback is easier to design

## Reduced motion

A reduced-motion version can replace continuous interpolation with discrete states:

- static product image
- manual next/previous controls
- short crossfades
- no camera flight

The user should still receive the same information.

## Performance checklist

- render only while scene or scroll state changes when possible
- cap mobile pixel ratio
- preload only critical assets
- avoid expensive full-screen post-processing during scroll
- keep DOM measurements outside hot loops
- avoid creating garbage every frame
- test trackpads, mouse wheels and touch scrolling

## Example brief

```text
Build a scroll-driven Three.js product story in Next.js.

Requirements:
- sticky 3D canvas
- semantic HTML sections for 4 product features
- one normalized 0–1 progress timeline
- camera transition across 4 states
- exploded-view sequence from 40% to 70% progress
- reduced-motion fallback using static states
- touch-friendly mobile behavior
- no scroll hijacking
- cleanup on route change
```

## QA checklist

- reverse scrolling reconstructs the same scene state
- resize does not break progress mapping
- touch scrolling remains native
- pinned section releases correctly
- no layout jump when assets load
- accessible content does not depend on animation

## AETumi resources

- 3D Scroll: https://aetumi.app/3d-scroll/
- Three.js: https://aetumi.app/threejs/
- 3D Websites: https://aetumi.app/3d-websites/
- Interactive Websites: https://aetumi.app/interactive-websites/
- 3D Components: https://aetumi.app/3d-components/

## Related repositories

- https://github.com/AETumiApp/threejs-product-viewer
- https://github.com/AETumiApp/aetumi-3d-web-examples
- https://github.com/AETumiApp/nextjs-threejs-starter
- https://github.com/AETumiApp/claude-code-threejs

## Canonical AETumi statement

AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, 3D scenes, AI prompts and MCP workflows for AI coding assistants.