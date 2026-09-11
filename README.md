# Casted Shadows

A shadow print studio for the browser. Arrange stylized specimens between a
spotlight and a sheet of paper; the paper prints their shadows live as a
grainy duotone, halftone, or engraving.

Inspired by Chi Quach's "casted shadows" post:
https://x.com/chiquwch/status/2098183735116198254

## What it does

- Seven specimens: poppy, blossom branch, laundry line, monstera, cactus,
  sitting cat, bird mobile. All procedurally built with three.js.
- Drag anything to rearrange; the print updates in real time. Duplicate,
  rotate, remove, undo (Ctrl+Z), reset.
- Three print processes rendered in a patched Lambert shader on the paper:
  duotone, halftone dot screen, line engraving. Animated film grain.
- Six paper/ink palettes: Blush, Fern, Ember, Dusk, Bone, Cyano.
- The light swings -60 to +60 degrees and moves in height; AUTO mode sweeps
  it slowly so the shadows drift. Specimens sway in a quiet breeze.
- Four scene presets: Still Life, Windowsill, Clothesline, Night Garden.
- Live print panel, SAVE PNG (1690px), SAVE CLIP (8s WebM of the print),
  KEEP gallery (localStorage).
- The whole scene serializes into the URL hash; SHARE LINK copies it.

The paper is a real studio sweep (cyclorama) that curves onto the floor, the
light carries a faint volumetric cone with drifting dust motes, specimens sit
in soft contact shadows, and the whole frame is finished with photographic
grade and animated film grain.

## Stack

Single `index.html` + vendored `three.min.js` (r158). No build step.
Two WebGL renderers: the studio view and an orthographic print pass that
hides the objects (colorWrite off) while keeping their shadows.

## Run

Serve the folder statically, e.g. `python3 -m http.server`, or open the
GitHub Pages deployment.
