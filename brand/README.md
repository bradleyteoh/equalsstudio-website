# Equals Design Studio — Brand Reference

## Logo

| Variant | File | Use |
|---|---|---|
| With background (cream) | `references/brand/logo-with-bg.jpeg` | Documents, presentations, email headers |
| Transparent background | `references/brand/logo-transparent.png` | Overlays, dark backgrounds, PDF embeds |

- Stacked brick icon forming an "E"
- Wordmark: EQUALS / DESIGN STUDIO
- Style: minimal, monochrome, architectural

## Color Palette

| Name | Hex | RGB | Use |
|---|---|---|---|
| Brand Black | `#1A1A1A` | 26, 26, 26 | Headers, primary text, borders |
| Brand Cream | `#E8E0D3` | 232, 224, 211 | Logo background, section fills |
| Light Cream | `#F5F2EE` | 245, 242, 238 | Alternating row tint |
| White | `#FFFFFF` | 255, 255, 255 | Base background |
| Muted Gray | `#888888` | 136, 136, 136 | Secondary text (addresses, captions) |

## Google Sheets API (RGB 0–1 scale)

```python
BRAND_BLACK = {"red": 0.102, "green": 0.102, "blue": 0.102}  # #1A1A1A
BRAND_CREAM = {"red": 0.910, "green": 0.878, "blue": 0.831}  # #E8E0D3
LIGHT_CREAM = {"red": 0.961, "green": 0.949, "blue": 0.933}  # #F5F2EE
WHITE       = {"red": 1.0,   "green": 1.0,   "blue": 1.0}    # #FFFFFF
MUTED       = {"red": 0.533, "green": 0.533, "blue": 0.533}  # #888888
```

## Typography

| Role | Font | Weight | Use |
|---|---|---|---|
| Primary typeface | DM Sans | Regular / Bold | All documents, sheets, PDFs |

- **Files:** `references/brand/fonts/DMSans-Regular.ttf`, `references/brand/fonts/DMSans-Bold.ttf`
- **Google Sheets:** Available natively as "DM Sans" in the font picker
- **PDF (fpdf2):** Embed via `add_font()` from the files above
- **Rationale:** Humanist proportions give warmth; geometric structure matches the architectural, minimal brand identity

## Usage conventions
- **Document headers**: Brand Black bg + White text
- **Section info blocks**: Brand Cream bg + Brand Black bold labels
- **Table alternating rows**: Light Cream / White
- **Body text**: Brand Black
- **Captions / secondary info**: Muted Gray
- **Borders (outer)**: Brand Black, weight 2
- **Borders (inner)**: Brand Cream, weight 1
