---
name: rm-design
version: 0.1.0
description: |
  Reservation Manager (RM) design guidelines enforcer. Routes to the WEB or
  MOBILE design system based on the requested surface and loads only that
  layer. These guidelines are derived strictly from the official RM Figma
  design-system files and MUST NOT be violated under any circumstance.
  Use when asked to "design", "create UI", "build a screen", "apply the RM
  design system", "design review", "use design guidelines", or any task that
  produces visual / UI output for Reservation Manager.
triggers:
  - design a screen
  - apply the RM design system
  - use the design system
  - build a UI
  - design review against guidelines
allowed-tools:
  - Read
  - Glob
  - Grep
  - AskUserQuestion
---

# /rm-design — Reservation Manager Design Guidelines

Strict enforcement of the **Reservation Manager** design system as defined in
Figma. There are **two parallel systems** — Web and Mobile. They are loaded
**conditionally**: load the one (or both) that the task targets. Do not mix a
web component into a mobile screen or vice-versa.

## Source of truth (Figma)

| Surface | Figma file | fileKey | Local copy |
| ------- | ---------- | ------- | ---------- |
| **Web** | [🔺📁🖥️ RM Web App Design System](https://www.figma.com/design/L7QMwEGtWjMB5ODihwnKiR/RM-Web-App-Design-System) | `L7QMwEGtWjMB5ODihwnKiR` | `web.md` |
| **Mobile** | [🔺📁📱 RM Mobile App Design System](https://www.figma.com/design/d1GJJKVRXmccqe5KIVU6Sc/RM-Mobile-App-Design-System) | `d1GJJKVRXmccqe5KIVU6Sc` | `mobile.md` |

Figma is canonical. If `web.md` / `mobile.md` ever disagree with Figma,
**Figma wins** — flag the drift to the user and update the local copy.

## Shared foundations (verified)

- **Color and typography are identical across web and mobile.** Same palette
  (brand `#C52031`, the Neutral / Error / Warning / Success / Prediction families,
  and the domain status colors) and the same Poppins type ramp. Both `web.md` and
  `mobile.md` carry the full values, so loading either layer alone is sufficient.
- What differs between surfaces is **components, layout, and spacing** — load the
  correct layer for those.

## Iron rules — non-negotiable

1. **Route, then load exactly one layer (or both).**
   - Web / website / dashboard / desktop / browser / responsive → read `web.md`.
   - Mobile / iOS / Android / app / phone / bottom sheet / native → read `mobile.md`.
   - Both surfaces in scope → read both, but keep their vocabularies separate.
   - Ambiguous → use `AskUserQuestion` to confirm **before** producing anything.
2. **Use ONLY the named styles and components** catalogued in the loaded layer.
   The style names (e.g. `Primary/Brand`, `Neutral/Content`, `Text/Md/Medium`)
   and component names (e.g. `Button`, `Dropdown`, `Top Navigation type 1`) are
   the authoritative vocabulary. Reference designs by these exact names.
3. **Do not invent token values.** Most exact values (hex, font size,
   line-height, spacing, radius, shadow) are marked
   `[VALUE NOT YET EXTRACTED FROM FIGMA]`. If a task needs a value that is not
   yet extracted, **stop and ask** — pull it from Figma first. Never guess a
   hex code, size, or spacing.
4. **Do not invent components.** If a needed component is not in the catalogue,
   first re-check Figma (the local copy is non-exhaustive — see Extraction
   status). If it genuinely does not exist, propose it explicitly and wait for
   confirmation. Do not silently improvise one.
5. **Do not violate, soften, or "modernize" any rule** to make a design work.
   If a request conflicts with the system, surface the conflict and ask the
   user to choose: change the request, or amend the system in Figma.

## Workflow — when this skill is invoked

1. **Detect surface** from the request (rule 1). Confirm if ambiguous.
2. **Load the layer** — read `web.md` and/or `mobile.md` in full.
3. **Plan against the catalogue.** Before writing code or visuals, draft a
   short checklist mapping the task to specific named styles + components from
   the loaded layer. Cite the section (e.g. "web.md §Color/Fill styles",
   "mobile.md §Components/Navigation").
4. **Flag any unresolved value** the task depends on, and resolve it from Figma
   (offer to fetch) before continuing — do not fill the gap by guessing.
5. **Produce the output**, staying strictly inside the loaded vocabulary.
6. **Self-review** against the iron rules. If anything was invented (a value, a
   component, an off-system color), fix it before reporting done.

## Resolving an unextracted value from Figma

When a needed style/value is marked unresolved:

1. Use the Figma MCP (`get_variable_defs` / `get_design_context` /
   `search_design_system`) against the `fileKey` for the surface.
2. `search_design_system` (scoped with the library key in `web.md` /
   `mobile.md`) enumerates components and styles by name.
3. `get_variable_defs` resolves a style/variable's value **only when it is
   bound to the queried node** — so you may need a node URL (`?node-id=…`) that
   uses the style. Ask the user for a node-specific Figma link if needed.
4. Once resolved, update the local `.md` file and replace the
   `[VALUE NOT YET EXTRACTED FROM FIGMA]` marker. Never edit the local file to
   reflect a value that did not come from Figma.

## Extraction status

Extracted from the published RM Figma libraries via the Figma MCP (June 2026).

- ✅ **Web** — complete: full color palette, Poppins type ramp, effect/shadow
  tokens, and specs for all 16 components (Button, Input, Dropdown/Tooltip, Popup,
  Sidebar, Header, Toast, Cards, Calendar, Tags, Logos, Toggle, Tabs, Table,
  Checkbox/Radio, Side drawer) + icon set.
- ✅ **Mobile** — complete: shared color + typography, plus specs for ~28
  components (Button, Icon Button, FAB, Input, Toast, Top/Bottom Nav, Tab bar,
  Reservation cards, Actions, Bottom Sheet, Table view, Tags, Filters, Dialog,
  Date/Time Picker, Dropdown, Chips, Checkbox, Radio, Calendar) + full icon library.

A few exact pixel dimensions remain flagged `[confirm]` in the layer files; treat
those as the only non-authoritative values. Everything else is verified from Figma.

**Web vs mobile differences to respect:**
- Checkbox & Radio: **web selects in brand-red `#C52031`; mobile selects in
  Success-green `#027A48`.** Do not cross them.
- `Digit` numeric badges use **Inter SemiBold**, not Poppins.

## When NOT to just apply rules

- "What does the RM system say about X" → answer from the docs; no output needed.
- "Update a guideline" → that's a Figma change. Don't edit `web.md`/`mobile.md`
  to reflect something not yet in Figma.
- "Off-system / experimental mockup" → require explicit acknowledgment ("yes,
  intentionally off-system") and clearly label the output as non-canonical.
