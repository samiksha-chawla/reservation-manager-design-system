# Reservation Manager Design System — Claude Code Plugin

The Petpooja **Reservation Manager (RM)** design guidelines, packaged as a Claude
Code plugin. It ships the `design-md` skill, which strictly enforces the RM design
system as defined in Figma. The skill **routes by surface** — it loads the **web**
or **mobile** guidelines (or both) depending on what you're designing.

## Install

In an interactive Claude Code terminal:

```
/plugin marketplace add samiksha-chawla/reservation-manager-design-system
/plugin install reservation-manager-design-system@reservation-manager-design
```

Then restart Claude Code (or reload plugins). The `design-md` skill activates when
you ask to "design", "create UI", "build a screen", "apply the RM design system",
or "design review".

## Pull updates

```
/plugin marketplace update reservation-manager-design
/plugin install reservation-manager-design-system@reservation-manager-design
```

## What's inside

```
skills/design-md/
  SKILL.md     # router + iron rules (web vs mobile)
  web.md       # RM Web App design system (color, type, effects, 16 components)
  mobile.md    # RM Mobile App design system (shared foundations + components)
```

## How it works

- **Color & typography are shared** across web and mobile (Poppins type ramp,
  brand red `#C52031`, neutral / semantic / domain-status palettes).
- **Components, layout and spacing differ** by surface — the skill loads the right
  layer for the task.
- All values are extracted **strictly from the official RM Figma files**; nothing is
  invented. A few exact pixel values are flagged `[confirm]`.
- Known web↔mobile differences are documented (e.g. Checkbox/Radio select in
  brand-red on web but Success-green on mobile; numeric `Digit` badges use Inter).

## Source

Maintained from `.claude/skills/design-md/` in the Reservation Manager project.
Figma source files:
- Web: `figma.com/design/L7QMwEGtWjMB5ODihwnKiR`
- Mobile: `figma.com/design/d1GJJKVRXmccqe5KIVU6Sc`
