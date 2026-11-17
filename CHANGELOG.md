# Changelog

## [2.0.0] - 2026-11-17

### Changed
- Upgraded to Pine Script v6.
- Renamed the MA variables to `priceLine` (2-period) and `signalLine` (7-period). They were previously labeled the wrong way around.
- The band multiplier is now an input (default 1.6185).

### Fixed
- Duplicate signals: a sharkfin now fires once per excursion outside the band, instead of on every cross within 10 bars of the excursion.
- The fast MA length input allowed 0, which caused a runtime error. The minimum is now 1.
- Removed the redundant `mid = (up + dn) / 2` calculation, which was identical to the band basis.

### Added
- Alert conditions for band-break warnings and buy/sell sharkfin signals.
- A "Require price line back inside band" option (re-entry mode).
- A "Signal only on closed bars" option, on by default, so live-bar signals don't flicker.
- An input for the maximum number of bars allowed between the excursion and the cross.

## [1.0.0]

- First version: TDI with out-of-band warning markers and cross signals within 10 bars of an excursion.
