# Hermes Ecosystem

A PKM tool ecosystem for creators — orchestrated by Hermes Agent.

> Built in public. Every decision documented. Every failure shown.

---

## What is this?

Hermes is not a tool. It's a **coordinator** for tools.

The problem: useful tools exist everywhere on GitHub — but they're scattered, unmaintained, or break when dependencies change. This ecosystem solves that by:

1. **Isolating each tool** in its own Docker container
2. **Defining clean I/O interfaces** between tools
3. **Letting Hermes orchestrate** the flow without touching tool internals

---

## Architecture

```
Hermes Agent (orchestration layer)
    │
    ├── Input Layer
    │     ├── yt-dlp          — video/audio fetching
    │     ├── myTranslator    — multilingual processing
    │     ├── Pandoc          — format conversion
    │     └── pdf-to-md       — PDF → Markdown (via marker + Gemini)
    │
    ├── Processing Layer
    │     ├── Graphify        — knowledge graph generation
    │     └── audiobook-pipeline  — text → M4B audiobook
    │
    └── Output Layer
          ├── Obsidian PKM    — knowledge storage
          └── YT Content      — teaching output
```

---

## Repositories

| Repo | Role | Status |
|------|------|--------|
| [hermes-ecosystem](https://github.com/xmei229/hermes-ecosystem) | This file. Overview + architecture. | ✅ Active |
| hermes-agent | Orchestration core | 🔧 Building |
| pdf-to-md | PDF → Markdown converter | 🔧 Building |
| audiobook-pipeline | Text → M4B audiobook | 📋 Planned |

---

## Design Principles

**Fork + freeze over blind updates**
Find a working version. Lock it. Don't chase upstream.

**One container per tool**
Dependency hell is isolated. One tool breaks, nothing else does.

**Adapter layer only**
No full maintenance. Only the interface that connects to Hermes.

---

## Follow Along

This ecosystem is being built in public as a YouTube tutorial series.

Target audience: **creators** — not necessarily developers.

The series covers not just *how* to build, but *why* each decision was made — including the failures.

> YouTube: *(coming soon)*

---

## License

MIT
