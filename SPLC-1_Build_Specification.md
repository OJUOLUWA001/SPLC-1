# SPLC-1 — Build Specification

Project: SPLC-1 sounding rocket, Orbithon WSW Hackathon 2026, Space Clubs LASU.
Status: design + simulation proposal. Verified in OpenRocket; no physical flight claimed.

Use this sheet to re-enter the design in OpenRocket from scratch, or to check a build against the proposal.

## 1. Nose cone
- Shape: Ogive, shape parameter 1
- Length: 12.7 cm
- Base diameter: 3.175 cm
- Wall thickness: 0.05 cm (estimated — no sourced manufacturer spec for disposable champagne-flute plastic)
- Material: Polycarbonate, 1.2 g/cm³
- Real-world part: a 2 oz plastic mini champagne flute, sanded/trimmed to match the standardised fuselage diameter

## 2. Body tube 1 — parachute bay
- Length: 10.5 cm
- OD: 3.175 cm / ID: 2.93 cm
- Wall thickness: 0.125 cm (estimated)
- Contains: Inner Tube with nested Parachute component
- Real-world part: a gas-relief pill bottle, also serving as the nose-to-body shoulder

## 3. Body tube 2 — fuselage
- Length: 35 cm
- OD: 3.175 cm / ID: 2.93 cm
- Wall thickness: 0.125 cm (estimated)
- Material: Polycarbonate approximation
- Real-world part: a golf club divider/organiser tube (1.25 in / 3.175 cm is a standard size for this product category)
- Contains: Engine Block, Launch Lug, motor mount

## 4. Engine block
- Length: 0.5 cm
- Outer/inner diameter: 2.96 cm (Automatic, tied to parent tube ID)
- Material: Cardboard, 0.68 g/cm³
- Position: bottom of parent component (Body tube 2)

## 5. Fin set
- Type: Freeform / trapezoidal, 3 fins
- Root chord: 12 cm
- Tip chord: 6 cm
- Height (span): 4.5 cm
- Thickness: 0.3 cm (3 mm)
- Sweep / cant: 0° / 0°
- Material: Balsa
- Mass: 6.2 g
- Fin tabs (through-the-wall mounting): tab length 6 cm, tab height 1.0 cm, tab position 3 cm (centred on root chord)

## 6. Launch lug
- Mounted on: Body tube 2 (fuselage), at or just below the rocket's CG, in line with the fins
- Length: 5–7 cm
- Inner diameter: ~0.5 cm (standard lightweight launch rod)

## 7. Motor
- Selection: Estes D12 (from OpenRocket's built-in motor database — real, published thrust-curve data)
- Diameter: 24 mm / Length: 70 mm
- Total impulse: ~17 N·s (D-class) / Average thrust: 12 N
- Loaded mass: ~42.6 g
- Note: tube ID (~29 mm) is wider than the 24 mm motor — a centering ring/adapter is needed in the motor mount for an actual build

## 8. Parachute — ⚠ OPEN ITEM, not finalized
Two different specs have been used at different points in this build and need reconciling before this is treated as locked:
- **Custom calculation (recommended default):** diameter 49 cm, ripstop nylon, Cd ~0.75–0.8 (Auto), mass ~20–30 g — sized for a ~5 m/s descent at ~218 g post-burnout mass
- **Commercial preset (selected later in the build via OpenRocket's Parts Library):** "SkyAngle Classic 32" — Cd 1.14, mass ~127 g (4.5 oz), ~32 in / 81 cm canopy
- Deployment: Apogee, 0 s delay
- Packed length: 3–5 cm (must fit inside the 10.5 cm parachute bay — this was the source of an earlier "tumble" simulation bug when accidentally set too large)

**Action needed:** confirm which of the two parachute specs is authoritative, then update the design and this document together.

## 9. Overall rocket (current model)
- Length: 60.7 cm / Max diameter: 3.175 cm
- Mass without motor: ~200 g / Mass with motor: ~242 g
- CG: 28.2 cm / CP: 51.2 cm
- Stability margin: ~7.2 cal (37.8%) — intentionally well past the 1–2 cal "ideal" range; trade-off is increased weathercocking (turning into wind) rather than any tumble risk

## 10. Simulation conditions used
- Launch site: Lagos, Nigeria (lat 6.5244° N, lon 3.3792° E), altitude ~15 m
- Launch rod: 1.0 m, 0° (vertical)
- Atmospheric model: standard ISA

| Condition | Avg wind | Wind SD | Turbulence |
|---|---|---|---|
| Baseline | 2 m/s | 0.4 m/s | 5–10% |
| Gust case | 5 m/s | ~1 m/s | 5–10% |

## 11. Simulation results

| Metric | 2 m/s baseline | 5 m/s gust case |
|---|---|---|
| Apogee | 171 m | 156 m |
| Max velocity | 53.6 m/s | 53.0 m/s |
| Max acceleration | 115 m/s² | 115 m/s² |
| Rod exit velocity | 13.6 m/s | 13.6 m/s |
| Time to apogee | 6.46 s | 6.18 s |
| Flight time | 48.8 s | 45.2 s |
| Ground hit velocity | ~5 m/s (target) | 6.88 m/s |
| Stability margin | 7.24 cal | 7.22 cal |

**Open caveat:** rod exit velocity (13.6 m/s) sits just under the commonly used 15 m/s guideline for reliable fin stabilisation off the rod. It's consistent across both wind conditions, so it's a real characteristic of this motor/mass combination — a longer launch rod would widen the margin.

## 12. Known open items (full list)
1. Parachute spec not reconciled (see section 8)
2. Pill bottle and golf-tube wall thickness are engineering estimates, not sourced manufacturer specs
3. Local motor sourcing in Nigeria is unconfirmed
4. Launch airspace/safety clearance is unconfirmed
5. Results are OpenRocket computational predictions, not physical flight validation
6. No onboard reading device — SPLC-1 carries no flight computer, altimeter, or GPS. Every figure in section 11 is a simulated prediction from the design's own geometry, mass, and the motor's published data, not measured telemetry from a real flight

---
Team: Agboola David (solo entrant)
Space Club member: Agboola David
