# Create a New Project

Use this prompt when the user wants to initiate a new website prototype project.

The user may provide any of the following:

- Project name
- Reference screenshots
- Mockups
- Website assets
- Supporting documents or requirements

## Workflow

1. Confirm the project name. Ask for it if it is not stated; use it as the project folder name.
2. Create or locate `/{project_name}` in the repository root. Do not treat `prompts/` as a project folder.
3. Organize provided materials using the repository convention:
   - `references/` — screenshots and visual-style references.
   - `mockups/` — primary visual references for building the HTML.
   - `resources/` — assets intended for use in the website.
   - Project root — supporting documentation such as requirements or content notes.
4. Create only the folders that are needed. Preserve provided filenames and avoid overwriting existing files without permission.
5. Follow the project’s `DESIGN_SYSTEM.md` when it exists. Place generated HTML in `{project_name}/outputs/` and follow all other instructions in `AGENTS.md`.
