---
type: concept
title: "Web Animations"
address: c-000024
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, frontend, design-assets
relevance: secondary
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Web Animations

The Web Animations workflow utilizes [[Claude Code]] to automate the translation of raw design assets (such as Adobe Illustrator or SVG code) into high-fidelity interactive web animations (e.g., SVG, React, Remotion).

## Core Pipeline

1. **Asset extraction**: Export raw vector assets from Adobe Illustrator as clean SVG code.
2. **Structural Ingestion**: Drop the SVG code into the staging `_raw/` directory.
3. **Remotion integration**: Have Claude Code wrap the SVG paths inside React components and animate them using Remotion or framer-motion keyframes.
4. **Automated render**: Run local render commands through the agent to export MP4 or GIF assets.

