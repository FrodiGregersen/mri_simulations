# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added
- Phantom panel: the bottom-left card is now titled "Phantom" with two tabs — "Tissue segmentation" (image + legend) and "Properties" (field strength, proton density, values table).
- Editable tissue values: selecting field strength "Manual" makes T1, T2, T2* and PD editable in the table; edits propagate to all figures and the simulated image. Custom values are kept when switching presets and restored on return to Manual; editing a value while a preset is selected auto-switches to Manual.
- Field strength selector (1.5 T / 3 T / Manual) and proton density checkbox moved into the phantom Properties tab.

### Changed
- Proton densities read from the tissue table everywhere (combined signal, recovery curves, chained panels, flip panel), so manual PD edits take effect across all plots.
- Proton density column in the values table reflects what is used: dimmed with values 1.00 when the proton density checkbox is off.
- Preset relaxation values shown as plain text in the values table; only Manual mode shows editable inputs.
- Removed the "Which relaxation time sets the TE decay" note under the Decay selector.

### Fixed
- Proton density edits previously had no effect (hardcoded PD array used for scaling).

## [Earlier]

### Added
- "Include full signal equation" tick on each figure (T1 recovery, T1 vs flip angle, T2 vs TE, phone T2 decay), right-aligned in the title. Tick on: T1 panels fold in proton density; T2 decay curves start from the current T1-stage signal instead of 1. Each tick affects only its own figure; ticks and the Proton density box work together.
- ⓘ info popups (hover/tap) next to each tick showing the full signal equation in serif math, adapting to Inversion and T2/T2* settings, with inactive factors grayed out.
- SVG subscript rendering for axis labels (M_z, |M_xy|).
- Proton density now defaults on.

### Changed
- Figure titles renamed to physical quantities: "Longitudinal recovery", "Signal vs flip angle", "Transverse decay", "Combined signal (normalised)"; parameter readouts (TR, flip angle) removed from titles.
- Y-axis labels stabilised to M_z and |M_xy| regardless of tick state.
- "● = Ernst angle" note moved to a separate right-aligned label at the bottom of the flip-angle figure.
- Info-popup equations expanded for inversion recovery: full M_ss expression, |…| magnitude form, and a proper inversion-mode recovery equation. Symbol definitions (M_z(TI⁻), M_ss) shown on separate lines below the equation; caption moved above it; sin(α)/cos(α) notation with parentheses.
- Info-popup grayed terms now match the actual data scaling per panel (PD grayed only when not included; T1-stage term grayed on the decay panel when the tick is off).

### Fixed
- Per-panel ticks work independently (duplicate-ID bug on the desktop T2 figure).
- ⓘ popup positioning: never off-screen, clipped, or collapsed.
- Refresh always resets settings to defaults.
