# Hero Block

## Overview

The Hero block displays a full-width banner with a background image and overlaid text content. It is typically used at the top of landing pages to create a visually impactful introduction with a headline, optional description text, and a call-to-action button.

## Integration

### Block Configuration

This block does not require any configuration parameters. Content is defined directly in the block structure with an image and text.

### Block Structure

The hero block is automatically created from a section containing a picture element followed by an `h1` heading. When both elements are present in the correct order, a hero block is auto-built.

Example authoring structure:
```
![Hero image](hero-image.jpg)

# Welcome to Our Store
```

## Behavior Patterns

### Layout Behavior

- **Full Width**: The hero spans the full width of the viewport, ignoring the standard section max-width constraint
- **Background Image**: The picture element is positioned as an absolute background that covers the entire hero area
- **Text Overlay**: Heading and paragraph text are rendered above the background image using z-index layering
- **Flexible Height**: Minimum height of 360px on mobile, 480px on desktop, expanding as needed for content
- **Vertical Centering**: Content is vertically centered using flexbox alignment

### Visual Design

- **Text Color**: Text is rendered in white (`var(--background-color)`) for contrast against the background image
- **Text Shadow**: Headings use a subtle shadow (`0 2px 4px rgb(0 0 0 / 40%)`) and body text uses a lighter shadow for readability
- **Left-aligned Text**: Content is left-aligned with a maximum width to maintain readability on wide screens
- **Responsive Padding**: 48px vertical padding on mobile, 80px on desktop for proportional spacing

### User Interaction Flows

1. **Page Load**: Hero image loads as a background, text and CTA are visible immediately
2. **CTA Button**: Any button links within the hero are styled and positioned above the background image

### Error Handling

- **Missing Image**: If no picture element is present, the hero renders without a background image
- **Missing Heading**: If no h1 is present, the hero renders without visible text overlay
