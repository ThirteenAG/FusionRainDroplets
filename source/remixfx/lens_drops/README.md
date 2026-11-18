# Lens Drops for RTX Remix (GTA IV)

Fusion Rain Droplets as a [RemixFX](https://github.com/xoxor4d/dxvk-remix/blob/game/gta4/docs/RemixFx.md) effect, for GTA IV with xoxor4d's [RTX Remix compatibility mod](https://github.com/xoxor4d/gta4-rtx) (gta4-rtx). Under Remix the frame is path traced and put on the screen right before the HUD, so the plugin's own drops never show. This effect draws the same drops inside the runtime instead, below the HUD.

It is a port of this repository, not a remake:

- **Simulation:** `source/xrd/xrd.h` (`SpawnDrops`, `CalculateMovement`, `MoveDrop`, `NewTrace`, `Fade`), run on the GPU over a pool of up to 4096 drops.
- **Drawing:** the quads `AddToRenderList` builds, drawn with the Direct3D 9 pixel shader (`source/shaders/d3d9/drops.hlsl`), its light field (`light.hlsl`) and a mip chain of the frame.
- **Shapes:** the atlas of drop shapes (`lensdrops.png`, the same file as `source/resources/lensdrops.png`).

Two things differ from the plugin:

- **Light Steadiness:** the light a drop gathers is carried over from the frames before. Against the path traced frame, a small light such as a tail light makes the glow flicker otherwise. Set it to 0 for the plugin's behaviour.
- **Trails:** the bands of water are drawn as one body, by the distance to their middle line, rather than as quads, so they have no seams.

Snow is not ported.

## Requirements

- gta4-rtx with the lens values (xoxor4d/gta4-rtx#192). It writes what the game asks the lens for (rain, blood, splashes, the fountain spray, the game's frame time) as game values.
- A Remix runtime that binds effect parameters to game values (`param.<id>.gamevalue`, xoxor4d/dxvk-remix#3), with `slangc.exe` beside the runtime or the game (see the RemixFX docs).

## Installation

Copy this folder into `remix-shaders` next to `GTAIV.exe` (`remix-shaders/lens_drops/`). The effect shows under External Effect Files in the Remix menu (Alt+X), where its settings are: the ones of the plugin's `.cfg`, plus Light Steadiness. Force Rain shows drops in any weather.

The plugin can stay installed. When gta4-rtx is loaded it stays out of the way, since both hook the same camera effect requests of the game.

`remixfx_bindings.slangh` is the runtime's RemixFX ABI header (MIT), shipped beside the effect as the runtime intends.
