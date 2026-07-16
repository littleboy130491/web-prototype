# Web Prototype Instructions

This repository contains independent rapid-prototype website projects. Treat each project folder as self-contained.

## Project workflow

1. Work only in the project folder relevant to the user’s request.
2. If present, read `<project>/DESIGN_SYSTEM.md` before designing and follow it to keep the HTML’s visual style consistent.
3. If present, inspect these folders before designing:
   - `references/` — screenshots and visual-style references.
   - `resources/` — website assets.
   - `mockups/` — primary visual references for building the HTML page.
4. Keep HTML implementation as simple as possible. Use Tailwind CSS through its CDN by default; add custom CSS only when necessary.
5. Put every generated HTML page and related prototype output in that project’s `outputs/` folder. Do not create HTML files elsewhere.
6. When the user asks for images generated with an image-generation skill (such as Imagen or `imagegen`), place them according to their intended use:
   - Mockups or images used as the primary visual reference for building HTML go in `mockups/`.
   - Images intended for use inside the website go in `resources/`.

The root `prompts/` folder is not a project. Read or modify it only when explicitly instructed; it contains saved and refined user prompts.
