# Until Then: Afterimages logo fix

Restores the missing **Afterimages** logo in the Nintendo Switch version of **Until Then 1.0.9** using the original texture from the PC version.

The texture is copied byte for byte, without resizing, recompression, or image editing. Its original import descriptor preserves the resource UID and points to the original Afterimages artwork.

[Русская инструкция](README.ru.md) · [Download ZIP](https://github.com/LunkezB/until-then-afterimages-fix/raw/refs/heads/main/releases/UntilThen-1.0.9-Afterimages-fix.zip) · [Technical details](docs/technical-notes.md)

## Installation

1. Close the game.
2. Download and extract `UntilThen-1.0.9-Afterimages-fix.zip`.
3. Copy the `atmosphere` directory to the root of the microSD card, merging directories and replacing the supplied files.
4. Launch Until Then 1.0.9 and select the first chapter of Afterimages.

## Compatibility

| Item | Value |
|---|---|
| Game | Until Then 1.0.9 / update v589824 |
| Program ID | `010019C023004000` |
| Afterimages DLC ID | `010019C023005002` |
| Installation | Atmosphère LayeredFS |

## Installed files

Under `atmosphere/contents/010019C023004000/romfs/`:

```text
.godot/imported/logo.png-4f17d4b89fcf9b35b1e430aa586bc8d4.ctex
scenes/_dlc_rdvt/ch1sc1a/assets/logo.png.import
```

The first file is the original 1256 × 170 Afterimages logo from the PC package. The second restores its missing import mapping. The scene structure, animations, and scripts remain intact.

## Validation

- Verified the texture against its entry in the PC package and checked its SHA-256.
- Loaded the original asset through the Texture2D scene reference in Godot 4.3.
- Checked the decoded pixels against the original PC image.
- Compared the logo node and title animation scripts between the PC and Switch versions.

**Confirmed on Nintendo Switch OLED with Until Then 1.0.9:** Afterimages opens successfully and displays the correct original logo. Checksums are in [manifest.json](manifest.json).

## Removal

Delete the two files listed above.
