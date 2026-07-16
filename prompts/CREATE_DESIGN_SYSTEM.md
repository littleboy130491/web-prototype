# Create a Design System

Use this prompt only when the user asks to create or formalize a design system. The system may be derived from `references/`, `mockups/`, an existing website, or the user’s direction.

## Workflow

1. Identify the relevant project folder `{project_name}`.
2. Inspect available references, mockups, assets, and existing project files.
3. Extract the visual rules that are actually present. Keep the system practical and avoid inventing unnecessary patterns.
4. Create:
   - `{project_name}/DESIGN_SYSTEM.md` — concise documentation of the system’s attributes and values.
   - `{project_name}/outputs/design-system.html` — a visual reference page for reviewing and adjusting the system.

## Document in `DESIGN_SYSTEM.md`

Include only relevant sections:

### Foundations

- Color palette and semantic color roles
- Typography families, sizes, weights, and line heights
- Spacing scale
- Container widths and grid rules
- Border radius, borders, and shadows
- Icon and image treatment
- Responsive breakpoints
- Animation and transition principles

### Components

Document reusable components such as buttons, links, form fields, cards, navigation, tabs, accordions, modals, notifications, pagination, and breadcrumbs when they are relevant.

For each component, define applicable states: default, hover, focus, active, disabled, loading, error, and selected.

### Layout and page patterns

Document reusable structures such as headers, footers, heroes, section wrappers, two-column layouts, card grids, sidebars, CTAs, logo/client grids, and common page types such as listing, detail, article, contact, service, case study, search, empty, and error pages.

### Responsive behavior

Explain how important layouts and components adapt across desktop, tablet, and mobile. Record concrete values where possible; label values inferred from references as recommendations.

## Build `design-system.html`

Create a simple, scannable visual showcase of the documented system, including:

- Color swatches with names and values
- Typography samples
- Spacing, radius, border, and shadow examples
- Component examples and relevant states
- Representative responsive layouts or page sections

Use simple HTML and Tailwind CSS through its CDN. Add custom CSS only when necessary. Keep the page easy to edit and ensure it demonstrates the documented values rather than introducing separate styles.
