# Restoring the original Afterimages logo

The first Afterimages scene, `rdvt.1.1a`, uses:

```text
res://scenes/_dlc_rdvt/ch1sc1a/Ch1Sc1a.tscn
```

Its external Texture2D resource is:

```text
res://scenes/_dlc_rdvt/ch1sc1a/assets/logo.png
UID: uid://dwwn2d187tpmn
```

The PC package contains both the import descriptor and the original texture:

```text
.godot/imported/logo.png-4f17d4b89fcf9b35b1e430aa586bc8d4.ctex
```

The Switch scene retains the resource reference, but these files were absent from the inspected Switch game/update dump and DLC file list. This package restores them using the PC asset and its import descriptor.

## Exact asset identity

| Property | Value |
|---|---|
| Texture size | 1256 × 170 |
| Compressed file size | 57,312 bytes |
| SHA-256 of the PC texture and installed copy | `f6bb37243b95d8f3b1d58495e5ee6dbee8e128d9be3b4f2605014c0289558169` |
| SHA-256 of decoded RGBA8 pixels | `0bd4e0db4961a913f882d836a4990d4a3a8ed063dd7b65b8ede194e8cfe3bb95` |

The compressed texture is copied unchanged. The import descriptor retains its importer, type, UID, original asset path, and texture metadata; only text line endings are normalized.

## Scene usage

In both versions, the resource is assigned to the `texture` property of:

```text
Root/World/Airport (1-7)/OpeningCredits/Logo
```

This is a TextureRect with a fixed 735 × 100 rectangle, centered anchors, and `EXPAND_IGNORE_SIZE`. It has no attached script. The PC source contains a single direct source/resource-text reference to the logo path, in this scene.

The `Credits` and `CreditsController` scripts match between the inspected PC and Switch versions after whitespace normalization. Their operations control visibility and opacity. Restoring the logo leaves those scripts and the scene's animation timing intact.

## Validation scope

The PC package identifies its export engine as Godot 4.1.4; the Switch executable identifies itself as Godot 4.3.1. The restored resource has been loaded successfully in Godot 4.3 and its decoded pixels checked against the PC asset.

On 2026-10-26, a physical Nintendo Switch OLED test with Until Then 1.0.9 confirmed successful entry into Afterimages and correct display of the original logo. This confirmation covers DLC startup and logo rendering; it does not constitute a complete gameplay run.
