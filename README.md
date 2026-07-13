# David Nichols

I build systems at the edge: software that has to work on a real Mac, with a real camera, against a real protocol, or inside a real developer workflow.

I’m a 17-year-old independent developer focused on edge ML, native macOS software, developer tools, and distributed systems. Most of my public work is exploratory and still evolving. The goal is to make each project more concrete, more testable, and more useful than the idea it started as.

[GitHub](https://github.com/davidnichols-ops) · [X](https://x.com/real_dnichols)

## What I’m building

### Edge computer vision

[apple-quality-recognition-engine](https://github.com/davidnichols-ops/apple-quality-recognition-engine) is an edge-first experiment for apple detection and quality grading. A vision model detects objects; a separate, inspectable policy is intended to make the grading decision. The project is aimed at Apple Silicon and Core ML, with the practical constraints of cameras, latency, and changing operational rules in mind.

### Protocols for agents

[AAFP](https://github.com/davidnichols-ops/aafp) is an experimental agent-to-agent networking project, supported by a [research repository](https://github.com/davidnichols-ops/AAFP-research) and a [Go interoperability implementation](https://github.com/davidnichols-ops/aafp-go). The work explores how a protocol can be specified clearly enough for independent implementations to agree. It is research and engineering practice—not a finished network or a claim of production adoption.

### macOS and developer tools

- [X-MaC](https://github.com/davidnichols-ops/X-MaC) — a Rust and SwiftUI system cleaner, optimizer, and monitor.
- [repo-archaeologist](https://github.com/davidnichols-ops/repo-archaeologist) — an offline tool for producing a first architectural briefing on an unfamiliar repository.
- [MacSift](https://github.com/davidnichols-ops/MacSift), [gargantua](https://github.com/davidnichols-ops/gargantua), [Sweeper](https://github.com/davidnichols-ops/Sweeper), and other small tools — experiments in safe cleanup, system inspection, and automation.

I also maintain smaller macOS utilities, a Photos export tool, a clipboard manager, menu-bar experiments, and a Manifest V3 version of [cloud-to-butt](https://github.com/davidnichols-ops/cloud-to-butt-revolutionized). Not every repository is a product; some are prototypes, learning projects, or tests of an idea.

## How I think about engineering

- Keep perception separate from policy. Models can suggest; explicit rules should explain decisions.
- Prefer a deterministic baseline that can be tested over an impressive demo that cannot.
- Treat hardware, malformed input, reconnects, and migration paths as part of the feature.
- Make destructive tooling cautious by default and show people what will happen before it happens.
- Use independent implementations and interoperability tests when a specification matters.
- Say what is experimental, what is working, and what is still unfinished.

## Current technical interests

Rust, Python, Go, TypeScript, Swift and JavaScript; Core ML and Apple Silicon; computer vision; QUIC and peer-to-peer systems; protocol design; command-line tools; SwiftUI; and practical automation for developers.

## Open source and upstream work

My profile is active, but it is still early. I have a growing collection of public projects, forks, prototypes, and experiments rather than a long record of mature products. I’m learning in public, opening issues and pull requests when I find problems that generalize, and trying to turn interesting ideas into software that can be tested by someone other than me.

I’m especially interested in opportunities involving computer vision, edge ML, systems programming, developer tools, or native Apple software.

## Status

This profile is a snapshot of work in progress. Repositories may change quickly, and project maturity varies. The code and documentation are the best guide to what is actually implemented.
