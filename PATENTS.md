# Patent & Trademark Notice

## Summary

The **L.E.A.P. design pattern** documented in this repository (the `.leap` file format, templates, and
examples) is shared openly under the MIT License so anyone may learn from and build with the pattern.

The **methods and systems** for latent-experience containerization and deterministic LLM state
instantiation — including but not limited to the "Seed and Shell" execution protocol, attention/KV-cache
state mapping, semantic scrubbing, latent boundary monitoring, and the associated runtime — are the
subject of a filed patent (**"System and Method for Latent Experience Containerization and Deterministic
LLM State Instantiation," filed 2026-01-13**) and are **patent pending**.

## What this means

- ✅ **Use the pattern.** Reading, authoring, and sharing `.leap` files and adapting the templates is
  encouraged under MIT.
- ⚠️ **No patent license is granted** by the MIT License or by publication of this specification. Rights
  in the patented methods/systems and the "Nitwyt" trademark are expressly reserved.
- 📩 **Commercial runtime / method use** — for the automated Nitwyt OS runtime and method implementations,
  contact the authors.

## Boundary (for maintainers)

Per Guardrail **G9 (Publication Boundary)**: this public repository contains **only** the `.leap`
spec/pattern. The Nitwyt OS runtime, the `_vault` (filed patent text + financials), API keys, and `.env`
files are private "owned cargo" and MUST NOT be committed here. Verify `.gitignore` before every push.
