# this-icon

An ever-expanding icon library designed for software interfaces.

## Overview

`this-icon` is an open-source SVG icon library providing multiple design styles to suit various UI needs. Each icon is carefully crafted and available in multiple formats.

## Icon Styles

The library includes icons in three distinct styles:

- **Solid** — Filled icons for bold, prominent use cases
- **Outline** — Line-based icons for clean, minimalist designs
- **Duotone** — Two-color icons for modern, playful interfaces

## Project Structure

```
this-icon/
├── icons/
│   ├── solid/          # Solid style SVG icons
│   ├── outline/        # Outline style SVG icons
│   └── duotone/        # Duotone style SVG icons
├── scripts/            # Build and automation scripts
├── package.json        # Project metadata and dependencies
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Getting Started

### Prerequisites

- Node.js (see `.nvmrc` for recommended version)
- npm (comes with Node.js)

### Installation

```bash
git clone https://github.com/signorchuksy/this-icon.git
cd this-icon
npm install
```

## Usage

Icons are stored as individual SVG files organized by style in the `icons/` directory.

### Accessing Icons

- Solid icons: `icons/solid/[icon-name].svg`
- Outline icons: `icons/outline/[icon-name].svg`
- Duotone icons: `icons/duotone/[icon-name].svg`

## Contributing

Contributions are welcome! To add new icons or improve existing ones:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/add-icons`)
3. Add your SVG icons following the naming conventions
4. Commit your changes (`git commit -m 'Add new icons'`)
5. Push to the branch (`git push origin feature/add-icons`)
6. Open a Pull Request

### Icon Naming Convention

- Use lowercase names with hyphens: `heart-outline.svg`
- Be descriptive: `arrow-up-right.svg` (not `arrow.svg`)
- Avoid style suffixes in filenames (style is determined by folder)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Created by [Chukwudi Ogbonnaya](https://github.com/signorchuksy)

## Repository

[github.com/signorchuksy/this-icon](https://github.com/signorchuksy/this-icon)
