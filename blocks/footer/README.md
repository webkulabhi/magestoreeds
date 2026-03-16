# Footer Block

## Overview

The Footer block renders the site footer, which includes navigational content loaded from a footer fragment and an optional store view switcher for multistore deployments. It provides a consistent bottom section across all pages.

## Integration

### Block Configuration

No block configuration is read via `readBlockConfig()`. The footer uses metadata tags for fragment paths.

### Metadata

The block reads the following metadata tags:

- `footer` - Path to footer fragment (default: `/footer`)

### Events

No events are emitted or listened to directly by this block.

## Behavior Patterns

### Store View Switcher

When the site is configured as a multistore deployment (`isMultistore()` returns `true`), the footer renders a store switcher button that opens a modal with the available store views. Users can select a different store view to switch context.

- Store switcher content is loaded from the `/store-switcher` fragment
- The currently active store is highlighted based on the current URL path
- Clicking a store view link switches the active store context

### Footer Content

When not in multistore mode, the footer simply renders the content loaded from the footer fragment path. This content is authored in the CMS and can include navigation links, legal text, and other footer content.

### Link Styling

Footer links use the neutral color scheme (`var(--color-neutral-700)`) and transition to a darker color (`var(--color-neutral-900)`) on hover with underline for accessibility.

## Error Handling

- **Missing Fragment**: If the store switcher fragment fails to load, an error is logged and the footer render is skipped
- **Fragment Fallback**: Uses default `/footer` path when metadata is not specified
