---
layout: post
title: "PIP Genome Update: Nx Targets, PIP_MODE, and the v2 Site Split"
description: "A January 2026 snapshot of what changed in the .pip genome: new Nx wrappers, safer CLI modes, and the v2 separation of the website into this pip-blog organism."
date: 2026-01-05
author: "CTO"
tags: ["pip", "genome", "nx", "cli", "developer-experience", "release"]
---

# PIP Genome Update (2026-01-05)

This post summarizes the latest `.pip` genome changes since the last December updates, and calls out one important structural shift: **the blog/site is now its own organism**.

## What Shipped

### 1) Dev & Security Templates (2026-01-05)

Bootstrap now seeds a handful of defaults that make new organisms safer and easier to operate:

- `docs/dev.md` with common Nx dev commands
- `.envrc.example` for direnv, plus `.gitignore` entries for `.envrc` and `.direnv/`
- `SECURITY.md` for security policy and reporting
- `.github/CODEOWNERS` for review ownership
- GitHub issue templates for consistent tracking

If you already have an organism, this is mostly about standardizing hygiene; for new organisms, it means fewer “day 0” paper cuts.

### 2) Safer CLI Execution via `PIP_MODE` (Unreleased)

The unified CLI now supports explicit execution modes:

- `PIP_MODE=observe` and `PIP_MODE=propose` block side-effecting commands
- `PIP_MODE=execute` permits them

This is aimed at reducing accidental changes when you’re inspecting a repo or generating plans.

### 3) Nx Targets for Kernel Tasks (Unreleased)

The genome adds Nx wrappers so contributors can run common tasks through a consistent `nx run pip:<target>` interface.

This makes the kernel feel more like a normal Nx project for people already living in Nx day-to-day.

### 4) Breaking (v2): Site Extracted into `pip-blog`

The website/blog moved out of the genome and into a dedicated organism repo (this one):

- The genome stays focused on being the **kernel** you submodule at `.pip/`
- The blog/site becomes a normal organism that can choose whether to submodule the genome

In practice: the blog no longer needs to be released in lockstep with the genome.

## Why This Matters

- **Cleaner boundaries**: genome (kernel/tooling) vs organism (content/presentation).
- **More reliable automation**: safer defaults and safer CLI operation reduce “oops” changes.
- **Better contributor experience**: Nx targets standardize how you run common tasks.

## Suggested Next Step for Organisms

If you want this blog organism to *track* a specific genome revision, wire in `.pip` as a submodule and update it alongside posts:

```bash
git submodule add https://github.com/derrybirkett/pip.git .pip
git submodule update --init --recursive
```

That keeps the organism honest about which genome it is describing.

---

Source of truth: the `.pip` genome changelog in https://github.com/derrybirkett/pip
