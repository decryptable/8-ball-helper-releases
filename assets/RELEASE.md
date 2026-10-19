# 8 Ball Helper v0.1.0

By decryptable. Autoplay and shot prediction for 8 Ball Duels (experience 10526463655, place 116921506811323). Uses bundled WindUI.

Enable Autoplay to play eligible turns. It starts off after every reload. RightShift toggles the window on desktop; minimize shows a floating button. Close or Unload removes the helper. Other experiences are rejected before loading the payload. Local prediction cannot guarantee wins.

## Latest release loader

```lua
if game.GameId ~= 10526463655 or game.PlaceId ~= 116921506811323 then return end
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/latest/download/8-ball-helper.luau"))()
```

## Pinned release loader

```lua
if game.GameId ~= 10526463655 or game.PlaceId ~= 116921506811323 then return end
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/download/v0.1.0/8-ball-helper.luau"))()
```

## Assets

- `8-ball-helper.luau`: minified, LZ4-packed standalone bundle.
- `loader-latest.luau` and `loader-version.luau`: loadstring loaders.
- `build.json`: version, WindUI commit, byte sizes, and bundle SHA-256.
- `SHA256SUMS`: asset checksums.
- `WindUI.LICENSE`: upstream license.

Re-execution removes the previous helper's UI, listeners, wrappers, and Drawing objects.
Unload from the UI or call `getgenv().__EightBallHelper.stop()`.

CI verifies formatting, tests, packing round-trips, and bundle compilation. It does not run Roblox.
Predictions use local game physics. Server outcomes and every live mode are not verified by CI.
