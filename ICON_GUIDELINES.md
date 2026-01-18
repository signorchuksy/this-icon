# Icon Guidelines

This document outlines the standards and best practices for creating icons in the `this-icon` library.

## Overview

The `this-icon` library is organized into three distinct style categories:

- **Solid** — Filled icons for bold, prominent visual emphasis
- **Outline** — Line-based icons for clean, minimalist interfaces
- **Duotone** — Two-color icons for modern, playful designs

## File Structure

```
icons/
├── solid/
│   ├── heart.svg
│   ├── star.svg
│   └── ...
├── outline/
│   ├── heart.svg
│   ├── star.svg
│   └── ...
└── duotone/
    ├── heart.svg
    ├── star.svg
    └── ...
```

Each style folder contains the same set of icon names, allowing users to switch between styles seamlessly.

## Naming Conventions

### Requirements

- **Lowercase letters only** — All filenames must be lowercase
- **Hyphens for separation** — Use hyphens to separate words, not underscores or camelCase
- **Descriptive names** — Names should clearly describe the icon's purpose
- **No style suffixes** — The style is determined by the folder; don't include it in the filename
- **No version numbers** — Don't add version suffixes to filenames

### Valid Examples

```
heart.svg
arrow-up.svg
arrow-up-right.svg
settings-gear.svg
user-profile.svg
check-circle.svg
close-x.svg
menu-hamburger.svg
trash-delete.svg
```

### Invalid Examples

```
Heart.svg              ❌ Not lowercase
arrow_up.svg           ❌ Uses underscore instead of hyphen
Arrow.svg              ❌ Not lowercase
arrow.svg (ambiguous)  ❌ Not descriptive enough
arrow-up-outline.svg   ❌ Don't include style in filename
```

## SVG Specifications

### Viewbox and Size

All icons should have consistent sizing:

- **Viewbox:** `0 0 24 24` (standard 24x24 grid)
- **Width/Height:** Should be explicitly set or default to viewBox dimensions
- **Aspect Ratio:** Always square (1:1 ratio)

```xml
<svg viewBox="0 0 24 24" width="24" height="24" xmlns="http://www.w3.org/2000/svg">
  <!-- icon content -->
</svg>
```

### Stroke and Fill

#### Solid Style
- Use filled shapes with `fill` property
- Typical fill color: `#000000` (black) or `currentColor` for theme support
- No stroke needed (or minimal)

```xml
<path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z" 
      fill="currentColor"/>
```

#### Outline Style
- Use strokes with minimal/no fill
- Stroke width: `1.5px` or `2px` (consistent across all outline icons)
- Fill: `none` or `transparent`
- Stroke color: `currentColor` or `#000000`

```xml
<path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z" 
      stroke="currentColor" 
      stroke-width="2" 
      fill="none" 
      stroke-linecap="round" 
      stroke-linejoin="round"/>
```

#### Duotone Style
- Use two distinct colors or opacity levels
- Primary color: `#000000` (or theme primary)
- Secondary color: `#000000` with 50% opacity (or theme secondary)
- Can use `fill-opacity` or separate color values

```xml
<g>
  <path d="..." fill="currentColor" opacity="1"/>
  <path d="..." fill="currentColor" opacity="0.5"/>
</g>
```

### Best Practices

1. **Simplicity First**
   - Remove unnecessary details
   - Use geometric shapes when possible
   - Avoid gradients unless essential to the duotone style

2. **Consistency**
   - Keep stroke widths consistent across all outline icons
   - Align shapes to the grid (multiples of 0.5 or 1 unit)
   - Use rounded corners consistently (if at all)

3. **Accessibility**
   - Use `currentColor` for colors so icons can be themed
   - Add meaningful alt text or titles if used in interactive elements
   - Ensure sufficient contrast (minimum 3:1 ratio)

4. **Performance**
   - Minimize path complexity
   - Remove metadata and comments in export
   - Avoid nested groups unless necessary
   - Optimize decimals (2 decimal places maximum)

5. **Stroke Details**
   - Use `stroke-linecap="round"` and `stroke-linejoin="round"` for outline style
   - Keep stroke width consistent (1.5 or 2 for 24x24 grid)

## Export Settings

When exporting icons from design software (Figma, Adobe XD, etc.):

1. **Export Format:** SVG
2. **Settings:**
   - Remove hidden layers
   - Convert text to outlines if any text is used
   - Flatten layers (if not needed separately)
   - Optimize SVG (remove unnecessary attributes)
3. **Post-Export:**
   - Remove `id` attributes (unless required for duotone colors)
   - Remove `style` attributes; use SVG attributes instead
   - Remove comments and metadata
   - Validate SVG structure

### Example Clean SVG

```xml
<?xml version="1.0" encoding="UTF-8"?>
<svg viewBox="0 0 24 24" width="24" height="24" xmlns="http://www.w3.org/2000/svg">
  <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z" 
        fill="currentColor"/>
</svg>
```

## Creating New Icons

### Step-by-Step Process

1. **Design** in your preferred tool (Figma, Illustrator, etc.) using a 24x24 artboard
2. **Create variants** for all three styles (solid, outline, duotone)
3. **Export** as SVG with clean settings (see Export Settings above)
4. **Name** according to conventions (lowercase, hyphens, descriptive)
5. **Place files** in appropriate style folders:
   - `icons/solid/icon-name.svg`
   - `icons/outline/icon-name.svg`
   - `icons/duotone/icon-name.svg`
6. **Test** visual consistency across styles
7. **Validate** SVG structure and remove unnecessary code
8. **Submit** via Pull Request with description

### Testing Your Icons

Before submitting, verify:

- [ ] Icon is centered in the 24x24 viewBox
- [ ] All three styles exist (or document why one is missing)
- [ ] Filename follows naming conventions
- [ ] File is in correct folder (solid/outline/duotone)
- [ ] SVG structure is clean (no unnecessary attributes)
- [ ] Icon looks good at multiple sizes (16x16, 24x24, 32x32, 48x48)
- [ ] Colors use `currentColor` for themability
- [ ] No inline `style` attributes

## Icon Sets

### When to Add New Icons

New icons should be added when they:

- Solve a clear use case not covered by existing icons
- Can be consistently represented across all three styles
- Maintain visual consistency with the library

### Icon Naming Strategy

Think of icon names in categories:

**Navigation/Direction:**
- `arrow-up`, `arrow-down`, `arrow-left`, `arrow-right`
- `arrow-up-right`, `arrow-down-left` (diagonal variants)
- `chevron-up`, `chevron-down` (for compact spacing)

**UI Controls:**
- `close-x`, `menu-hamburger`, `search-magnifying-glass`
- `plus`, `minus`, `equals`

**Status Indicators:**
- `check-circle`, `x-circle`, `warning-triangle`
- `info-circle`, `question-mark`

**Actions/Objects:**
- `heart`, `star`, `flag`
- `trash-delete`, `settings-gear`, `user-profile`

## Common Issues and Solutions

### Issue: Icon looks distorted at small sizes
**Solution:** Simplify the design and avoid thin strokes that disappear at small sizes

### Issue: Outline style looks too thin or thick
**Solution:** Ensure consistent stroke-width (1.5 or 2px) across all outline icons

### Issue: Duotone colors don't match the brand
**Solution:** Use CSS to override colors via `fill` or `color` properties for theme support

### Issue: Icon has extra whitespace
**Solution:** Ensure viewBox coordinates match the actual content bounds; use artboard crop feature

## Questions or Contributions?

For questions about icon standards or to propose new icons, please open an issue on the [GitHub repository](https://github.com/signorchuksy/this-icon/issues).
