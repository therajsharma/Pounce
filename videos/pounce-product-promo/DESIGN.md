# Design System

## Overview

Pounce is a light, security-product dashboard with a precise SaaS interface structure: sticky navigation, a large hero message, a dashboard preview, verdict rows, queue panels, and trust-state modules. The page uses warm off-white surfaces with dark ink, teal as the primary trust accent, steel blue for system context, amber for warnings, and muted red for blocks. Typography is bold and compact, with Outfit for product copy and Geist Mono or IBM Plex Mono for commands, verdicts, and package names. The overall feel is local-first, auditable, and agent-workflow focused.

## Colors

- **Primary Ink**: `#18181B` - main headline and high-emphasis UI text.
- **Ink Soft**: `#3F4749` - secondary labels and supporting copy.
- **Muted Text**: `#69726F` - body copy, small metadata, and low-priority status.
- **Page Surface**: `#F7F8F4` - warm page background.
- **Soft Blue Surface**: `#EEF4F7` - cool dashboard and section tint.
- **White Surface**: `#FFFFFF` - modules, queue items, and buttons.
- **Dark Surface**: `#17201F` - header strip, primary CTA, and high-contrast security panels.
- **Trust Teal**: `#0E7669` - protected status, allow state, and live pulse.
- **Allow Green**: `#287665` - allow verdict rows and positive statuses.
- **Warn Amber**: `#A56B1D` - warning verdicts and release review.
- **Block Red**: `#A84638` - block verdicts and malicious-package stops.
- **Steel Blue**: `#365F73` - system context, feed state, and connector lines.

## Typography

- **Primary Sans**: Outfit, weights 400-900. Used for hero headlines, dashboard labels, CTA text, and explanatory copy. Headline sizing reaches 70px plus in the source hero.
- **Monospace**: Geist Mono, IBM Plex Mono, JetBrains Mono, or system monospace. Used for command strips, package names, exact releases, verdict codes, and terminal-like details.
- **Hierarchy**: Hero text is oversized and heavy. Module titles are compact but bold. Labels and code are small, readable, and tightly grouped, never decorative.

## Elevation

Depth comes from thin borders, soft translucent surfaces, and restrained shadows. The dashboard uses 1px border lines, subtle warm/cool surface shifts, glass-like panels, and soft box shadows rather than heavy dimensional effects. Motion should preserve this: camera drift, panel slides, typed command reveals, and live pulse accents are better than explosive effects.

## Components

- **Sticky Security Header**: dark advisory bar above a glass navigation shell with pill CTAs.
- **Hero Command Strip**: two-line terminal command block with muted mono type and a steel prompt marker.
- **Workspace Snapshot Panel**: large dashboard card with protected pill, verdict rows, metric rail, and live queue.
- **Verdict Route Rows**: allow, warn, and block rows with thin colored left edges and package names in mono.
- **Live Queue**: compact queue cards for blocked packages, warning hooks, workspace sweeps, and feed trust.
- **Signal Stream Chips**: horizontal row of compact ALLOW, WARN, BLOCK, TRUST, and HOOK chips.
- **Feed Trust Modules**: source precedence rows showing hosted feed, local cache, and bundled seed fallback.

## Do's and Don'ts

### Do's

- Use light warm surfaces and dark ink as the default canvas.
- Keep teal, amber, red, and steel accents tied to security meaning.
- Use thin borders, subtle shadows, and dashboard layers to create depth.
- Use real package examples from the site: `jose@6.2.2`, `axios@1.15.0`, and `plain-crypto-js@4.2.1`.
- Keep command and package text in monospace.

### Don'ts

- Do not turn the promo into a dark neon cyber interface.
- Do not replace verdict semantics with generic colored decoration.
- Do not use large generic gradients as the main visual language.
- Do not make text-only beats; the dashboard and product UI must stay visible.
- Do not use rounded pill overload beyond the existing CTA and status patterns.
