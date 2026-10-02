# Web Royale Classic v0.50.3

This artwork patch replaces the earlier Touchdown reference texture with the
original stadium from the supplied Clash Royale **16.402.2** XAPK. Classic keeps
its historical **102-card / 3.2557.2** gameplay snapshot and battle engine. The
verified build is live on GitHub Pages, with its published bundle checked in Chrome.

## Original Touchdown artwork

The original `level_touchdown_arena` scene supplies the pitch, stands, entrances,
statues, flags and audience. All **168 source placements** retain their location
and layer metadata, with zero unresolved export references. Its three scene
dependencies—`level_touchdown_arena`, `source_touchdown_decos` and
`source_touchdown_bootcamp`—use **2,545,130 bytes** of lossless texture files.

Separate pitch/turf, backdrop and lighting compositions contain unchanged source
frame entries. Source animation is sampled where authored. Source **white
goal-strip centers 56.8333333 / 578.5** align with existing logical scoring lines
**25 / 615**, preserving normal and wide Touchdown's playable geometry. Colored
end-zone band centers are not used as scoring anchors.

The renderer now draws **1,902 source triangle chunks with flat UV samples**
that the affine-only texture path skipped. It samples their original texel and
fills the authored polygons, preserving the original goals, transverse lines
and yard ticks. No replacement field markings are invented.

Animation-mode cache invalidation applies only to the original source stadium.
Other maps retain their static scenery caches when ambient animation is toggled.

This supersedes the prior 551×647 reference-texture stadium and statements that
complete original 2D Touchdown artwork was unavailable. The source import does
not establish complete native shaders, dynamic shadows, ambient cloud/blimp
effects, separate light emitters or universal animated-backdrop parity.

## Preserved Classic scope

Classic retains **14 Trophy Road arenas plus Training Camp**, its historical
balance, progression, card rules and replay simulations. Its compatible modern
portrait/animation refresh and three original seasonal tower styles—Shark Tank,
Sandcastle and Fortress—remain as described in
[v0.50.2](BUILD-NOTES-v0.50.2.md). No modern cards, Heroes, Evolutions or Main 3D
actor content are introduced by this patch.

The source mapping and goal measurements are in
[`assets/native/touchdown-arena.json`](assets/native/touchdown-arena.json).
This remains a browser recreation with local opponents, economy and social
systems. Complete 1:1 native-game fidelity remains unverified; there is no live
online matchmaking or Supercell account/service connection.

## Verification status

The final Node suite passed **1,281/1,281 tests**, with zero failures or skips.
Actual Chrome checks of `app.8b38dc84289b.js` passed Touchdown, Touchdown 2v2 and
Touchdown 3v3 at four viewport sizes, including phone touch deployment, source
animation clocks and original goal-mark pixels. These checks use the shipped
bundle and source scene artwork, with no replacement renderer. The focused
scenery/flat-UV/source-stadium regression suite passed **14/14 tests**.

The verified website contains **1,226 files / 376,042,124 bytes**. Its release
digest is
`abce0a20cacd540de99ad5e1ad9b3ec3de46afe2fe271f7c7cf4be5d7d5b8498`.
Source restoration and release-file integrity checks passed. This identifies the
website payload, separately from an editable project archive.

The patch is [live on GitHub Pages](https://ocey78.github.io/web-royale-classic/).
[Deployment run 37002557880](https://github.com/Ocey78/web-royale-classic/actions/runs/37002557880)
succeeded for commit `c0de4619d346608c3fc2ffc5fb00a81cf3150f90`. The published
`app.8b38dc84289b.js` and release digest matched the verified local build. Actual
Chrome checks of the public site passed original seasonal skins, Rocket, all
three Touchdown modes across four viewports, phone touch deployment, source
animation clocks and original goal-mark pixels, with no browser or asset errors.
