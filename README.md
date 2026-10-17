# 落桜の塔 · Pagoda of Falling Blossoms

A voxel-art garden scene: a five-tier pagoda in a Japanese garden with cherry blossoms,
a koi pond with waterfall, a hanami viewing deck, a zen rock garden — rendered in the browser
with three.js, generated procedurally as ~16,900 colored voxels baked into instanced meshes.

## Files

| File | Purpose |
|---|---|
| `pagoda-garden.html` | The complete scene. Single self-contained file — open directly in Chrome. |

No build step, no dependencies installed locally — three.js r170 is pulled from the
jsDelivr CDN on first load (requires an internet connection for the initial open;
the page shows a friendly message if the CDN can't be reached).

## Original prompt

> Design and create a very creative, elaborate and detailed voxel art scene
> of a pagoda in a beautiful garden with trees, include some cherry blossoms. Make the scene impressive and varied and use colorful voxels. Use whatever libraries to get this done but make sure I can paste it all into a single HTML file and open it in chrome. Use playwright mcp to test the page.

## Model used

| | |
|---|---|
| Model | GLM-5.3-Flash Free |
| Provider | opencode |
| Model ID | glm-5.3-flash-free |

## Scene contents

- **Five-tier pagoda** — vermilion pillars, cream plaster walls, gold bracket cornices,
  slate roofs with gold eave trim, downturned corner eaves with wind bells, glowing
  windows, lantern-lit entrance, golden spire with diamond rings
- **Koi pond** — sandy shallows, stone lip, shoreline reeds, lily pads with lotus
  blooms, 4 swimming koi visible through translucent water, 26 pulsing sun glints,
  and a mossy **waterfall rockery** pouring into the east lip with a foam ring
- **Cherry blossoms** — five sakura trees with procedurally built branches and pink
  ellipsoid canopies; 420 falling petals spawn from the crowns and drift down,
  collecting under the canopies — and **settling flat on the pond surface** for a
  while before respawn (verified: ~35 afloat at any time)
- **Garden features** — arched red bridge, torii gate, tea house with glowing doorway,
  8 stone tōrō lanterns, pines, gradient-crowned maples, bamboo groves, bushes,
  flower beds, rocks, gravel paths
- **Zen rock garden** — raked gravel discs with dark groove rings, stone border,
  mossy island with a boulder, its own tōrō
- **Hanami viewing deck** — wood deck over the south shore with posts, rail and a lit
  paper-lantern pole; two paper parasols (red on the deck, cream near the tea house)
- **Festival lantern row** — two dark poles with a sagging string of 7 glowing lanterns
  across the south walk
- **Living background** — 6 birds flapping in wide circles, 3 butterflies over the
  flowerbeds, drifting voxel clouds, patrolling dragonflies, gradient sky dome,
  **sea of clouds with two hazed mountain ranges + golden sun with halo**,
  ACES tone mapping, soft shadows

## Controls

- Drag to orbit · scroll to zoom · right-drag to pan
- 🌸 toggles the falling petals, 🔄 toggles auto-rotation
  (auto-spin stops when you grab the scene)

## Testing

Built and iterated against [Playwright MCP](https://github.com/microsoft/playwright-mcp):
screenshots from five camera angles, zero console errors, and programmatic verification
of both UI toggles. The second pass (waterfall, zen garden, deck, lanterns, background
world) was re-verified the same way, plus a runtime census of floating petals via
`window.__dbg.petDat`. Gallery screenshots: `pg_final_hero2.png` (wide), `pg_v3_wf.png`
(waterfall), `pg_v4_zen.png` (zen garden), `pg_final_pond2.png` (aerial, gallery)
captured during the sessions.
