# One Photon

A single continuous zoom from a sunlit leaf down to the four manganese atoms that take an oxygen molecule out of water. Nine orders of magnitude, 10⁻¹ m → 10⁻¹⁰ m, no cuts.

**▶ [Watch it](https://allensanborn.github.io/photon-journey/)** — about two minutes. One HTML file, no dependencies, no build step.

## What it is

Ten stations along one dolly shot:

| # | Station | Field of view | What is on screen |
|---|---|---|---|
| 1 | A leaf in sunlight | 10 cm | blade, midrib, two orders of vein reticulation |
| 2 | Through the epidermis | 355 µm | cuticle, epidermis, palisade and spongy mesophyll, a stoma |
| 3 | One palisade cell | 45 µm | wall, vacuole, nucleus, chloroplasts streaming round the periphery |
| 4 | Inside a chloroplast | 5.6 µm | double envelope, stroma, grana, stroma lamellae, a starch grain |
| 5 | A granum | 631 nm | 14 appressed discs, 450 nm across, 17.5 nm repeat |
| 6 | The thylakoid membrane | 100 nm | 4 nm bilayer, PSII supercomplexes, cytochrome b6f, lumen at pH 5 |
| 7 | Photosystem II | 28 nm | C₂S₂ supercomplex, LHCII trimers, the excitation walking the antenna |
| 8 | Charge separation | 8.9 nm | P680 → pheophytin → Q_A → Q_B, with its time constants |
| 9 | The oxygen-evolving complex | 1.6 nm | Mn₄CaO₅, the Kok cycle counting to four |
| 10 | 2 H₂O → O₂ + 4 H⁺ + 4 e⁻ | 891 pm | the O–O bond forming, 121 pm, and the oxygen leaving |

Then it pulls back out and follows the O₂ through the stoma.

## The one rule that makes it work

**Everything is drawn in real metres.** There is a single world coordinate system whose origin is the Mn₄CaO₅ cluster, and every structure is placed at its true size relative to it. The camera is one number — `log₁₀` of the field-of-view width — and the projection is `metres ÷ metres-per-pixel`. Layers fade in and out over log-scale windows rather than being cut between.

That constraint is doing real work. The scale bar and the field-of-view readout are not decoration; they are read straight off the projection, so if a structure were drawn at the wrong size it would be visibly wrong against the bar. A granum with the wrong disc pitch cannot be hidden.

## Reading the controls

- **Space** play / pause, **←** / **→** jump a station
- Drag the scrubber, or deep-link: `?s=7` jumps to station 8 (zero-indexed), `?t=42` to 42 seconds, add `&still=1` to hold the frame
- Sound is off until you turn it on. It is a drone whose filter opens as the scale closes, plus one note per station — generated in WebAudio, nothing is loaded.

## Accuracy notes

Sizes, time constants and redox potentials are textbook values, shown on screen where they matter. A few deliberate simplifications:

- The whole journey below station 1 is a **cut-away**, a standard leaf-anatomy convention. The face-on blade opens into cross-section rather than the camera physically boring through the epidermis.
- Protein complexes are rendered as space-filling envelopes at correct dimensions and correct membrane topology, not as solved structures. Cofactor positions in the PSII reaction centre follow the real chain and its ~1.1–1.7 nm spacings.
- The Mn₄CaO₅ cluster is drawn with the right composition and connectivity — a Mn₃CaO₄ cubane plus a dangling fourth Mn — laid out in two dimensions.
- Time is compressed unevenly. Excitation transfer really is ~100 fs per hop and the rate-limiting S₃ → S₀ step really is ~1.3 ms; the animation plays them at comparable speeds so both are visible.
- Photosystem I and ATP synthase are named but kept out of the appressed membrane, where they genuinely do not fit.

## License

MIT. See [LICENSE](LICENSE).
