# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added
- "Include full signal equation" tick on each figure (T1 recovery, T1 vs flip angle, T2 vs TE, phone T2 decay), right-aligned in the title. Tick on: T1 panels fold in proton density; T2 decay curves start from the current T1-stage signal instead of 1. Each tick affects only its own figure; ticks and the Proton density box work together.
- ⓘ info popups (hover/tap) next to each tick showing the full signal equation in serif math, adapting to Inversion and T2/T2* settings, with inactive factors grayed out.
- SVG subscript rendering for axis labels (M_z, |M_xy|).
- Proton density now defaults on.

### Changed
- Figure titles renamed to physical quantities: "Longitudinal recovery", "Signal vs flip angle", "Transverse decay", "Combined signal (normalised)"; parameter readouts (TR, flip angle) removed from titles.
- Y-axis labels stabilised to M_z and |M_xy| regardless of tick state.
- "● = Ernst angle" note moved to a separate right-aligned label at the bottom of the flip-angle figure.

### Fixed
- Per-panel ticks work independently (duplicate-ID bug on the desktop T2 figure).
- ⓘ popup positioning: never off-screen, clipped, or collapsed.
- Refresh always resets settings to defaults.
