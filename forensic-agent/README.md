# Forensic motion collection

Six animated states built from the selected investigation agent, option 08. The original silhouette, face geometry, and single-color style are preserved.

Open index.html in a browser for the interactive preview. It works locally without a build step or a server.

## The states

| State | Loop | Intended use |
| --- | --- | --- |
| Idle | 4.8 s | A quiet breath and an occasional blink. Ready for the next clue. |
| Scanning | 3.2 s | The optical eye sweeps for a signal while the reticle turns. |
| Inspecting | 3.6 s | A curious tilt and raised brow bring a clue into focus. |
| Thinking | 2.4 s | Three small signals work through the evidence inside the lens. |
| Found | 2.2 s | The reticle resolves into a check, followed by an acknowledging nod. |
| Alert | 2.4 s | An attention gesture and a clear caution mark flag something to review. |

Each state is available in svg/. preview.gif is a synchronized moving overview; preview.png is a still comparison. The GIF aligns the loops for comparison, while the SVGs retain the timings listed above. forensic-static.svg is the approved unanimated original.

## Use an animation

Reference a file as an ordinary image, for example:

```html
<img src="svg/scanning.svg" width="64" height="64" alt="Investigating">
```

All files are true SVG vectors with transparent backgrounds and CSS keyframes. They contain no JavaScript, fonts, raster images, or external dependencies. They use a 128 × 128 viewBox and can be scaled to any square size. Animation is supported in modern web browsers; design-tool SVG importers may show a static frame.

## Color and playback

- Standalone images render black by default. Inline an SVG to inherit the surrounding CSS color. For a standalone SVG/image file, set color="#176B5B" on its root element. CSS color on an img element does not recolor the SVG contents.
- For inline SVG, data-paused="true" on its root pauses motion. Remove it or set it to false to resume.
- SVGs respect the operating system's prefers-reduced-motion setting. data-reduced-motion="true" explicitly selects a readable static state; false explicitly opts into full motion.
- Found and Alert loop for demonstration. In a real interface, switch away from these states when the relevant result or notice is dismissed.
- Give each embedded instance unique IDs when repeating the same SVG inline. The gallery handles this automatically.

The gallery pauses its animation when hidden or offscreen. Apply the same behavior when integrating an inline SVG into an app: use IntersectionObserver and the visibilitychange event to update data-paused. If using SVG image URLs, replace the src with forensic-static.svg when the image is offscreen or the document is hidden.

## Preview controls

Choose a state, pause or replay it, change playback speed, switch the stage background, or preview reduced motion. Only the selected state animates; the six navigation thumbnails stay still.
