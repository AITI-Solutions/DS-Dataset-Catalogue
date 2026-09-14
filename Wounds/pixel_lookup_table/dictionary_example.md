# Data Dictionary

# overlay-pixel-value-lookup

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| tissue_type | String | Name of the tissue/skin category represented by this overlay layer | Granulation | 18 distinct values: Boundary, PeriWoundPerimeter, WoundPerimeter, Epithellialization, Granulation, Hypergranulation, NecroticSlough, Eschar, OtherWound, DamagedToeNail, HealthyToeNail, Oedematous, Erythematous, OtherSkinUnbroken, Maceration, Excoriation, OtherSkinBroken, HealthySkin |
| colour | String | Display colour assigned to this tissue type, as a CSS colour name or hex code | yellow | CSS colour name (e.g. silver, cyan, yellow) or hex code (e.g. #00b7eb) |
| overlay_save_value | String | Bitmask value used to encode/save this tissue type in the overlay file format | 0x8000 | Hexadecimal string; one bit set per tissue type, 18 distinct values ranging 0x0100–0x800000 |
| overlay_save_value_rgb1 | String | First RGB-channel decomposition of the overlay save value (used for storing the bitmask across image channels) | (0, 128, 0) | `(R, G, B)` tuple string, integer 0–255 per channel |
| overlay_save_value_rgb2 | String | Second RGB-channel decomposition of the overlay save value | (0, 128, 32) | `(R, G, B)` tuple string, integer 0–255 per channel |
| colour_rgb | String | RGB value of the display colour, for rendering | (255, 255, 0) | `(R, G, B)` tuple string, integer 0–255 per channel |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- Source file: `overlay-pixel-value-lookup.csv` — 18 records, 6 columns, fully populated (no nulls).
- This is a static reference/lookup table (not a data record set) mapping each wound/skin tissue type to its overlay encoding (`overlay_save_value` and its RGB channel decompositions) and its display colour (`colour` / `colour_rgb`).
- `overlay_save_value` values are single-bit hex flags (e.g. 0x0100, 0x0200, 0x0400 ... 0x800000), consistent with a bitmask scheme where each tissue type occupies one bit — allowing multiple tissue types to be encoded/combined per pixel.

