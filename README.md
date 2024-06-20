# Planet Field Boundary Extension Specification

- **Title:** Planet Field Boundary
- **Identifier:** <https://fiboa.github.io/planet-fb-extension/v0.1.0/schema.yaml>
- **Property Name Prefix:** planet
- **Extension Maturity Classification:** Proposal
- **Owner**: @cholmes

This document explains the Planet Field Boundary Extension to the
[Field Boundaries for Agriculture (fiboa) Specification](https://github.com/fiboa/specification).

This is the place to add a short introduction.

- Examples:
  - [GeoJSON](examples/geojson/)
  - [GeoParquet](examples/geoparquet/)
- [Schema](schema/schema.yaml)
- [Changelog](./CHANGELOG.md)

## Properties

The properties in the table below can be used in these parts of fiboa documents:

- [ ] Collection
- [x] Feature Properties

| Property Name   | Type   | Description |
| --------------- | ------ | ----------- |
| planet:mcid | float | **REQUIRED**.Maximum Inscribed Circle Diameter (MICD)  is an intuitive proxy for the width of a field, even in case of rotated and narrow-but-curved fields.  |
| planet:ca_ratio | float  | The ratio is calculated by dividing the circumference of a given polygon by the square root of its area. This ratio is then adjusted so that a circle corresponds to 0, and scaled so that a square corresponds to 1 |
| planet:qa | uint8 | Quality Assessment attribute |

The ‘qa’ attribute presents three values:
  0) Polygons for which the validation
scores are representative, i.e. with
MICD > 30 m.
 1) Polygons for which the validation
scores are not representative, i.e. with
MICD < 30 m. The quality for these
polygons cannot be guaranteed.
 2) Polygons that are intersecting the
border of the data availability grid

## Contributing

See the [contributing guideline](CONTRIBUTING.md) for more details.
