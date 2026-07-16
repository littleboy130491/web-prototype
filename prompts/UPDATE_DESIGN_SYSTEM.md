# Update an Existing Design System

Use this prompt when the user wants to revise or extend an existing project’s design system based on new references, a changed visual direction, or explicit design feedback.

Before starting, read `prompts/CREATE_DESIGN_SYSTEM.md` and follow its conventions. This is an update workflow: preserve valid existing decisions, change only what the new evidence or requirements justify, and keep the documentation and visual showcase synchronized.

## Reference selection

Identify the relevant project folder `{project_name}`. Use the user’s newly supplied reference, mockup, website, asset, or design direction as the primary source of change. Also inspect the project’s existing:

- `DESIGN_SYSTEM.md`
- `outputs/design-system.html`
- `references/`
- `mockups/`
- `resources/`
- representative HTML pages when needed to understand current usage

If the user has not provided or clearly identified a reference, ask what should be used as the source of truth before making visual changes. If the reference is clear, proceed without asking for confirmation.

## Workflow

1. Confirm `{project_name}` and work only inside that project folder. Do not treat `prompts/` as a project.
2. Compare the current design system with the new reference or requirements.
3. Separate confirmed changes from values that remain valid. Do not replace the whole system merely because one area changed.
4. Update both files:
   - `{project_name}/DESIGN_SYSTEM.md` — concise documentation of the current system’s attributes, values, states, and responsive rules.
   - `{project_name}/outputs/design-system.html` — an editable visual reference page that demonstrates the documented system.
5. Keep both files aligned: every important documented value should be represented in the showcase where practical, and the showcase must not introduce undocumented styles.
6. Review the result at desktop and mobile widths. Check that the updated rules are legible, coherent, and consistent with the reference.

## Update `DESIGN_SYSTEM.md`

Retain relevant existing sections and revise only what has changed. Include, when applicable:

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

Document only components that are used or clearly required. For each relevant component, describe its anatomy, variants, and applicable states: default, hover, focus, active, disabled, loading, error, and selected.

### Layout and page patterns

Document reusable structures such as headers, footers, heroes, section wrappers, two-column layouts, card grids, sidebars, CTAs, logo/client grids, and relevant listing, detail, article, contact, service, case study, search, empty, or error patterns.

### Responsive behavior

Explain how important layouts and components adapt across desktop, tablet, and mobile. Record concrete values where possible. Clearly label values inferred from references as recommendations rather than established facts.

When the update changes a token or shared rule, note its semantic role and any important downstream effect on components or page patterns. Avoid documenting speculative tokens or patterns that are not supported by the project or reference.

## Update `outputs/design-system.html`

Keep the showcase simple, scannable, and easy to edit. Update it to include the relevant parts of the revised system:

- Color swatches with names, semantic roles, and values
- Typography samples with family, size, weight, and line-height examples
- Spacing, radius, border, and shadow examples
- Component variants and relevant interaction states
- Representative layout or page-pattern examples
- Responsive behavior where it materially affects the system

Use simple HTML and Tailwind CSS through its CDN by default. Add custom CSS only when necessary. Reuse project assets when appropriate, avoid adding unrelated content, and ensure the page demonstrates the documented values instead of creating a second visual language.

## Completion criteria

The update is complete when:

- The revised system reflects the user’s reference or direction.
- Existing valid rules have been preserved unless there is a clear reason to change them.
- `DESIGN_SYSTEM.md` and `outputs/design-system.html` describe and show the same system.
- Responsive behavior and important component states are represented.
- No HTML output was created outside the project’s `outputs/` folder.
- The final response briefly summarizes the meaningful changes and identifies any inferred recommendations.
