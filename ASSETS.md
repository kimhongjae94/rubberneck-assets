# RUBBERNECK — third-party assets and licenses

Everything in the game is generated in code (building, furniture, textures, sounds, stretchy neck) except the
realistic character models listed here. Character models are **not** inside the game HTML: in production they are
loaded from the public asset repository through jsDelivr (`src/characters/ModelLoader.js`, `CDN_BASE`).

## Character models

All characters are built by `tools/models/build_character.py` from a JSON spec in `tools/models/characters/`
with **Blender 5.2.2** + **MPFB 2.0.17** (MakeHuman for Blender). Tools are GPL; that does not apply to what they
produce. The MakeHuman base mesh, targets and the "MakeHuman system assets" pack are **CC0 1.0** (public domain),
and so are the exported models.

| Model | File | Made from (all CC0, MakeHuman system assets pack) | Our changes |
|---|---|---|---|
| Gary (player) | `models/gary.glb` (434 KB) | base mesh + macro/detail targets, rig `default`, proxy `male_generic`, skin `middleage_caucasian_male`, eyes `low-poly` (brown), `eyebrow001`, `eyelashes01`, `teeth_base`, clothes `male_casualsuit02`, `shoes02` | body shape targets; shirt re-baked as a striped knit sweater (our procedural stripes); head split off at the neck for the stretchy neck; decimated; textures ≤ 1024 px WebP; meshopt compression |
| Brad (102) | `models/brad.glb` (508 KB) | male_muscle_13290, skin young_caucasian_male2, eyes low-poly (blue), eyebrow001, eyelashes01, teeth_base, hair short02, male_casualsuit05, shoes06 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Dale (301) | `models/dale.glb` (497 KB) | male_generic, skin middleage_asian_male, eyes low-poly (brown), eyebrow001, eyelashes01, teeth_base, hair short03, male_worksuit01, shoes04 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Ellie (402) | `models/ellie.glb` (536 KB) | female_generic, skin young_asian_female, eyes low-poly (green), eyebrow002, eyelashes02, teeth_base, hair ponytail01, female_sportsuit01, shoes05 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Mr. Hollis (101) | `models/hollis.glb` (612 KB) | male_generic, skin old_caucasian_male, eyes low-poly (grey), eyebrow001, eyelashes01, teeth_base, hair short04, male_casualsuit03, shoes01 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Mrs. Pickles (201) | `models/pickles.glb` (495 KB) | female_generic, skin old_caucasian_female, eyes low-poly (brownlight), eyebrow002, eyelashes02, teeth_base, hair bob02, female_elegantsuit01, shoes03 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Rosa (202) | `models/rosa.glb` (653 KB) | female_generic, skin middleage_african_female, eyes low-poly (brown), eyebrow002, eyelashes02, teeth_base, hair afro01, female_casualsuit02, shoes05 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |
| Mr. Vance (401) | `models/vance.glb` (553 KB) | male_generic, skin middleage_caucasian_male, eyes low-poly (ice), eyebrow001, eyelashes01, teeth_base, hair short01, male_elegantsuit01, shoes02 | body shape targets; decimated; textures ≤ 1024 px WebP (eyes/teeth/brows 256, hair 512); meshopt |

Sources:
- MakeHuman system assets (CC0): https://static.makehumancommunity.org/assets/assetpacks/makehuman_system_assets.html
- MPFB: https://extensions.blender.org/add-ons/mpfb/ (GPL-3.0-or-later, tool only)
- Blender: https://www.blender.org (GPL, tool only)

## Monsters and mission props (made for this game)

Built entirely by our own Blender scripts in `tools/models/creatures/*.py` (skin-modifier skeletons, procedural
sculpting, procedurally baked textures) — no third-party meshes or textures. Dedicated to the public domain (CC0 1.0)
together with the rest of this asset repository.

| Model | File | Body plan · colours |
|---|---|---|
| The Magnet | `models/c_magnet.glb` | knuckle-walking iron heap, red horseshoe-magnet head, nails / keys / forks / chains · black iron, rust, red |
| The Lantern Keeper | `models/c_lantern.glb` | hooded robe, 14 back tentacles, hooked claws, staff with lantern · moss green, amber |
| The Mass | `models/c_mass.glb` | legless rubbery heap on two huge arms, tall toothed mouth, horns · violet / indigo |
| The Watcher | `models/c_watcher.glb` | floating orb covered in eyes, 7 tendrils · teal |
| The Hollow | `models/c_hollow.glb` | walking dead tree, branch antlers, twig fingers, glowing face holes · grey-brown bark |
| The Spindle (boss) | `models/c_spindle.glb` | small body on eight very long legs, cluster of red eyes · bone white, black |
| Mission props | `models/c_props.glb` | brass key, candle, music box, glowing fruit, red egg |

## Animations

None as files. All motion (sitting, walking, the monsters' gaits, tentacles, head following) is code: bones are
aimed/rotated at runtime. No Mixamo assets are used anywhere.

## Libraries bundled in the game HTML

- three.js r186 — MIT (https://github.com/mrdoob/three.js), including GLTFLoader and the meshoptimizer decoder (MIT).
