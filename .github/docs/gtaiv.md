<div align="center">

<a href="https://www.youtube.com/watch?v=IiEXixRWUMU"><img src="https://i.imgur.com/MyQAw7f.png" width="760" alt="Fusion Rain Droplets in GTA IV"></a>

[Download](https://github.com/ThirteenAG/FusionRainDroplets/releases/download/gtaiv/GTAIV.FusionRainDroplets.zip) · [Source Code](https://github.com/ThirteenAG/FusionRainDroplets/blob/master/source/GTAIV.XboxRainDroplets.cpp)

</div>

---

## Installation

1. Download and install [GTA IV Fusion Fix](https://github.com/ThirteenAG/GTAIV.EFLC.FusionFix#readme), or the required [ASI Loader](https://github.com/ThirteenAG/Ultimate-ASI-Loader).
2. Download [Fusion Rain Droplets for GTA IV](https://github.com/ThirteenAG/FusionRainDroplets/releases/download/gtaiv/GTAIV.FusionRainDroplets.zip) and put the `.asi` file into the `plugins` folder.
3. Launch the game - the drops of the effect are visible while it rains.

Used Xbox Rain Droplets before? Delete the old `GTAIV.XboxRainDroplets.asi`: while it is there, the game shows a message and closes.

## RTX Remix

With xoxor4d's [RTX Remix compatibility mod](https://github.com/xoxor4d/gta4-rtx) the plugin's drops can't show, because the path traced frame is put on the screen over them. The drops come from the RemixFX port of the effect instead: copy [`source/remixfx/lens_drops`](../../source/remixfx/lens_drops) into `remix-shaders` next to `GTAIV.exe`, and see its [readme](../../source/remixfx/lens_drops/README.md) for what it needs. The plugin stays out of the way while the mod is loaded.

## Notes

- Works with the Complete Edition, and with the episodes the plugin is installed for (`EFLC.exe`).
- Change the settings on [fusionfix.io](https://fusionfix.io), in FusionFixHub, or in the game with GTA IV's Fusion Fix (its menu and the Ctrl+F10 overlay); changes apply while the game runs. They are stored in the `.cfg` next to the plugin.
