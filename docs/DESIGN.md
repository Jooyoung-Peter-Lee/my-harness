# DESIGN.md — Design System & Visual Language

## Design Philosophy

> **Fill in:** What is the core visual and interaction philosophy? (e.g., "minimal, functional, fast")

---

## Design System

| Element | Specification | Notes |
|---|---|---|
| Component library | (e.g., shadcn/ui, Radix, MUI) | |
| CSS approach | (e.g., Tailwind CSS, CSS Modules) | |
| Icon set | (e.g., Lucide, Heroicons) | |
| Font | (e.g., Inter, Geist) | |
| Design tokens | (e.g., `src/styles/tokens.css`) | |

See [design-system-reference-llms.txt](references/design-system-reference-llms.txt) for full component API reference.

---

## Color Palette

| Token | Value | Usage |
|---|---|---|
| `--color-primary` | (fill in) | Primary actions, links |
| `--color-secondary` | (fill in) | Secondary actions |
| `--color-destructive` | (fill in) | Delete, error states |
| `--color-muted` | (fill in) | Subtle text, borders |
| `--color-background` | (fill in) | Page background |

---

## Typography Scale

| Token | Size | Usage |
|---|---|---|
| `text-xs` | 12px | Captions, labels |
| `text-sm` | 14px | Body small |
| `text-base` | 16px | Body default |
| `text-lg` | 18px | Subheadings |
| `text-xl`+ | 20px+ | Headings |

---

## Spacing & Layout

- Base unit: 4px
- Grid: (e.g., 12-column, max-width 1280px)
- Breakpoints: `sm` 640px · `md` 768px · `lg` 1024px · `xl` 1280px

---

## Component Conventions

- Prefer composition over configuration
- Every interactive element must have a visible focus state
- All form fields require associated labels (accessibility)
- Loading states: skeleton > spinner > empty state

---

## Accessibility Standards

- WCAG 2.1 AA minimum
- Color contrast ratio ≥ 4.5:1 for text
- All images have `alt` text
- Keyboard navigation fully supported
