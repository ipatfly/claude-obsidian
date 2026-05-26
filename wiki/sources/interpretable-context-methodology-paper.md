---
type: source
title: "Interpretable Context Methodology: Folder Structure as Agent Architecture"
address: c-000027
created: 2026-05-26
updated: 2026-05-26
tags:
  - source
  - paper
  - architecture
  - context-engineering
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Interpretable Context Methodology: Folder Structure as Agent Architecture

Authors: [[Jake Van Clief]], [[David McDermott]] (Eduba, University of Edinburgh)
Date: March 18, 2026

## Summary

This paper introduces the [[Interpreted Context Methodology]] (ICM), which replaces complex, code-heavy AI orchestration frameworks (like LangChain or AutoGen) with a simple, transparent folder structure combined with markdown files.

Instead of writing multi-agent coordination code, ICM uses a **5-Layer Context Hierarchy** (folders and files) to orchestrate sequential AI workflows. The filesystem itself acts as the orchestration logic.

## Practical Implementation of Workspaces

When building a workspace based on this schema, practitioners should focus on the following core principles:

1. **One Stage, One Job:** 
   Break workflows into discrete folders (e.g., `01_research/`, `02_script/`, `03_production/`). Each stage does exactly one thing and passes its output to the next stage's folder.
2. **Layered Context Loading:**
   Instead of stuffing all prompts and knowledge into one massive prompt, separate them into layers. The model only reads the context relevant to the *current stage*. This prevents the "lost in the middle" degradation where LLMs ignore relevant context.
3. **The "Stage Contract" (CONTEXT.md):**
   Every stage folder contains a `CONTEXT.md` file defining:
   - **Inputs:** What files to read (Layer 3 reference material & Layer 4 working artifacts)
   - **Process:** What the agent should do
   - **Outputs:** Where the agent should save its work
4. **Every Output is an Edit Surface:**
   Because intermediate outputs are saved as plain text/markdown files in an `output/` folder, humans can open, review, and manually edit the output before running the next stage. This creates a highly observable, "glass-box" system where humans can steer the AI perfectly (Semantic Debugging).

## Defining the Scope of a Workspace

A workspace is defined as a single, self-contained directory that encompasses an entire sequential pipeline for a specific, repeatable task. 

- **Scope boundaries:** The scope is defined by the workflow. If a pipeline takes unstructured research and produces a slide deck, the entire pipeline (from extraction to final assembly) lives in one workspace folder.
- **Portability:** A workspace can be zipped, emailed, or committed to Git. Because it has no server infrastructure or database dependencies, the folder *is* the application.
- **Configure the Factory, Not the Product:** The workspace scope includes the "factory" (reference materials, rules, voice guidelines in `_config/` or `references/`). The product (the working artifacts in `output/`) changes every run, but the factory remains stable.

## Real-World Use Case Examples

The paper cites several production use cases where this methodology has been successfully deployed:

1. **Script-to-Animation Pipeline:** 
   A 3-stage workspace (`01_research`, `02_script`, `03_production`) that takes a topic brief, researches it, writes a script following a voice guide, and finally produces React-based Remotion code for an animated video.
2. **Course Deck Production:**
   A 5-stage workspace that takes unstructured source material (PDFs, papers, notes) and converts them into polished PowerPoint slide decks (Content Extraction → Structural Planning → Slide Drafting → Visual Design Specification → Final Assembly). The human intervenes primarily at the structural planning stage.
3. **Workspace Builder:**
   A meta-workspace (a 5-stage pipeline) designed to create *new* workspaces by interviewing the user about their domain, mapping stages, and scaffolding the folder structure.
4. **Academic & Policy Workflows:**
   Adopted by the Neuropolitics Lab at the University of Edinburgh and the Academy of International Affairs in Bonn for literature review, synthesis, and policy analysis workflows.
