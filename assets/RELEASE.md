# 8 Ball Helper v0.1.3

By decryptable. Autoplay and shot prediction for 8 Ball Duels (experience 10526463655, place 116921506811323). Uses bundled WindUI.

Enable Autoplay to play eligible turns. It starts off after every reload. RightShift toggles the window on desktop; minimize shows a floating button. The native close button asks for confirmation before removing the helper. Other experiences are rejected before loading the payload.

## Changes

- Dynamic preview follows actual aim, charge, spin and equipped cue stats. The separate Preview Power control is removed. Native overlay lines remain visible in valid aiming states across modes.
- Trickshot planning verifies full-star routes through remaining cue balls, including setup shots, community scene data, patrols and rotors. Joint power/spin sampling and diverse goal subsets avoid greedy partial clears. Failed moving windows receive bounded replanning.
- Match planning respects solid/stripe assignment and samples up to three plies, including opponent responses and legal defensive shots. Manual cursor input cannot override an active Autoplay action.
- Eligible earned rewards are claimed automatically, including the normal post-win card flow.
- The panel contains only Autoplay and Overlay. Close confirmation uses black text on white, with Roblox translation disabled for the helper's English UI.

Live verification on place version 441 completed Pendulums with maximum stars in one timed shot. An isolated native Hourglass fixture verified a full two-cue route. Local tests cover 129 core assertions; native tests cover physics/rules, challenge routes, Autoplay lifecycle and close confirmation. These checks do not establish a competitive win rate or guarantee every community challenge.

If the primary search fails, a bounded recovery pass tries verified safeties and cushion kicks. Release code uses renamed functions and masked compressed blocks, opened once at startup. Autoplay runs ordinary Luau without a VM obfuscator. Obfuscation remains reversible by someone controlling the executor.

## Latest release loader

```lua
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/latest/download/8-ball-helper.luau"))()
```

## Pinned release loader

```lua
loadstring(game:HttpGet("https://github.com/decryptable/8-ball-helper-releases/releases/download/v0.1.3/8-ball-helper.luau"))()
```

## Assets

- `8-ball-helper.luau`: obfuscated, masked LZ4-packed standalone bundle with an internal experience guard.
- `loader-latest.luau` and `loader-version.luau`: loadstring loaders.
- `build.json`: version, WindUI commit, byte sizes, and bundle SHA-256.
- `SHA256SUMS`: asset checksums.
- `WindUI.LICENSE`: upstream license.

Re-execution removes the previous helper's UI, listeners, wrappers, and overlay objects.
Confirm the native close dialog or call `getgenv().__EightBallHelper.stop()`.

CI verifies formatting, tests, packing round-trips, and bundle compilation. It does not run Roblox.
Predictions use local game physics. Server outcomes and every live mode are not verified by CI.
