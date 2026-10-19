# 8 Ball Helper v0.1.2

By decryptable. Autoplay and shot prediction for 8 Ball Duels (experience 10526463655, place 116921506811323). Uses bundled WindUI.

Enable Autoplay to play eligible turns. It starts off after every reload. RightShift toggles the window on desktop; minimize shows a floating button. Close or Unload removes the helper. Other experiences are rejected before loading the payload. Local prediction cannot guarantee wins.

If the primary search fails, a bounded recovery pass tries verified safeties and cushion kicks. Release code uses renamed functions and masked compressed blocks, opened once at startup. Autoplay runs ordinary Luau without a VM obfuscator. Obfuscation remains reversible by someone controlling the executor.

## Latest release loader

```lua
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/latest/download/8-ball-helper.luau"))()
```

## Pinned release loader

```lua
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/download/v0.1.2/8-ball-helper.luau"))()
```

## Assets

- `8-ball-helper.luau`: obfuscated, masked LZ4-packed standalone bundle with an internal experience guard.
- `loader-latest.luau` and `loader-version.luau`: loadstring loaders.
- `build.json`: version, WindUI commit, byte sizes, and bundle SHA-256.
- `SHA256SUMS`: asset checksums.
- `WindUI.LICENSE`: upstream license.

Re-execution removes the previous helper's UI, listeners, wrappers, and Drawing objects.
Unload from the UI or call `getgenv().__EightBallHelper.stop()`.

CI verifies formatting, tests, packing round-trips, and bundle compilation. It does not run Roblox.
Predictions use local game physics. Server outcomes and every live mode are not verified by CI.
