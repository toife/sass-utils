# @toife/sass-utils

Sass library for design tokens, utility classes, and theme generation. No build step required — use raw Sass files directly in your project.

## Installation

```bash
npm install @toife/sass-utils
# or
yarn add @toife/sass-utils
# or
pnpm add @toife/sass-utils
```

## Usage

### Basic import

```scss
@use "@toife/sass-utils";
```

### Use config, functions, mixins, generators

```scss
@use "@toife/sass-utils" as sass-utils;

// Config (prefix, separator)
// Functions: fn-naming-*, fn-color-*
// Mixins: mx-palette, mx-tokens
// Generators: classes-generate, properties-generate
```

### Example: Generate utility classes

```scss
@use "@toife/sass-utils" as sass-utils;

@include sass-utils.generate();
```

### Example: Generate theme from tokens

```scss
@use "@toife/sass-utils" as sass-utils;

$theme: (
  "spacing": (...),
  "layers": (...),
  "shapes": (...),
  "sizes": (...),
  "palette": (...)
);

@include sass-utils.properties-generate("light", $theme);
```

## API

| Namespace | Description |
|-----------|-------------|
| `config` | `$prefix`, `$separator` variables |
| `fn-naming-*` | Naming functions (prefix, property, var...) |
| `fn-color-*` | Color utilities (palette, mix, tint, shade...) |
| `mx-*` | Mixins (palette, tokens) |
| `classes-*` | Utility class generators (spacing, flex, display...) |
| `properties-*` | Theme/token generators (layers, shapes, tokens) |

## Peer dependency

- `sass` >= 1.50.0
