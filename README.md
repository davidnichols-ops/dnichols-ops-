# David Nichols

**Building systems that have to be right on real hardware.** 17. Edge-first. The work lives at the boundary where a model's opinion stops and an auditable decision has to be made.

[![X](https://img.shields.io/badge/follow-%40real_dnichols-000000?logo=x&style=social)](https://x.com/real_dnichols)

---

## What I'm Working On

Two threads, pulled in parallel.

The first is **edge computer vision that grades fruit on a conveyor** — a real Arducam, a real M4, a real harvest deadline. The model detects; a deterministic policy file decides. The second is **AAFP**, a post-quantum P2P networking stack for autonomous agents — QUIC, ML-DSA-65 identity, a Kademlia DHT, and an Intelligence Plane above a frozen wire format.

One is small and physical. One is large and abstract. Both are exercises in the same instinct: separate the part that should be stable from the part that should evolve, and make the boundary explicit.

---

## Engineering Philosophy

These are observations I keep arriving at, not slogans I started with.

**Neural networks identify. Algorithms decide.** Judgment does not belong in floating-point weights. Put the decision logic in config, make it auditable, and let the network do what networks are good at — perception. A facility rule change should not require retraining.

**Freeze the wire, evolve above it.** The protocol is not the place to be clever. Bake interfaces, not algorithms. The acid test for any addition: does it make the system more capable, or merely more complicated? If it's merely complicated, it belongs in an implementation, not the spec.

**A working deterministic version beats a broken AI version.** Ship the heuristic first. Label it as an estimate. No fake precision. Add the LLM later, when it earns its place.

**Hardware reliability is table stakes, not an afterthought.** Cameras drop. Indexes enumerate wrong. The system has to reconnect, auto-detect, and keep grading. "Validated against the wrong camera" is a real failure mode I have shipped and then fixed.

**Read-only by default. Destructive actions commented out.** A scan that can't break your machine is a scan people will actually run. Remediation scripts get reviewed by a human before anything runs.

**Reality remains the final authority.** A neural network can be wrong about a fruit. A system misaligned with facility rules is useless. The README should say what's pending, not what's impressive.

---

## Current Interests

- **Edge ML on Apple Silicon** — CoreML, the Neural Engine, and the gap between a notebook model and a pipeline that survives a real camera.
- **Distributed systems and protocol design** — DHTs at scale, NAT traversal, post-quantum handshakes, and what it takes to make a spec unambiguous enough to implement twice.
- **Developer tooling** — tools that read a system or a repo and tell you something true, with zero config and no API key.
- **Native macOS software** — Swift, SwiftUI, and apps that feel like they belong on the machine.

---

## Open Source

I work mostly solo, and I treat open source as a way to ship tools I'd want to use myself.

The pattern is consistent: I hit a wall, build the tool that clears it, and release it. `repo-archaeologist` exists because inherited repos are unreadable. `X-MaC` exists because macOS developer environments rot. `mif_env_mapper` exists because nobody should hand-type a system inventory. `cloud-to-butt-revolutionized` exists because a decade-old joke extension died on Manifest V2 and that felt wrong.

I open PRs upstream when the fix is general — the cloud-to-butt MV3 migration went back to the original author. I write independent second implementations to prove a spec is real, not to pad a graph.

---

## Selected Projects

### [apple-quality-recognition-engine](https://github.com/davidnichols-ops/apple-quality-recognition-engine)
Real-time CV pipeline for apple variety detection and USDA-style grading, built for the family orchard. YOLO26 detects; a `grading_policy.yaml` file grades. Defects bind to apples via Intersection-over-Area. Low-confidence frames are harvested as free training data. Runs on the Apple Neural Engine through CoreML. This is the project where my principles actually have to hold up against a piece of fruit.

### [AAFP](https://github.com/davidnichols-ops/aafp) · [research umbrella](https://github.com/davidnichols-ops/AAFP-research) · [Go interop](https://github.com/davidnichols-ops/aafp-go)
A post-quantum, agent-first P2P networking stack. Rust reference (19 crates, ~140K lines), a TypeScript SDK, and a Go implementation written strictly from the RFCs to validate that the wire format is unambiguous. The transport is frozen at Rev 6; the work above it is an Intelligence Plane — predictive routing, intent routing, reputation, pubsub. The competitor is not HTTP. The competitor is cloud silos that own the agent graph.

### [X-MaC](https://github.com/davidnichols-ops/X-MaC)
A macOS system sanitizer and discovery tool in Rust. Every engine is read-only. Privacy redaction is on by default — home paths, tokens, keys, emails, IPs. Remediation scripts are emitted with destructive commands commented out and paths shell-quoted against injection. The `envmap` engine is a port of `mif_env_mapper`, which is how ideas graduate from prototype to production here.

### [repo-archaeologist](https://github.com/davidnichols-ops/repo-archaeologist)
Point it at an abandoned repo. Get an opinionated architecture, risk, and onboarding briefing in seconds. Zero runtime deps, offline, deterministic. The v1 deliberately avoids LLM prose — a working heuristic is more useful than a broken AI version.

### [Futurist](https://github.com/davidnichols-ops/word_proc)
A minimalist macOS writing app in Swift. One pane, monospace, true-black. Tab word completion from built-in, resource, and document vocabularies. The icon is rendered procedurally in CoreGraphics — a few hundred lines of code, not a binary blob. No network, no bloat.

### [cloud-to-butt-revolutionized](https://github.com/davidnichols-ops/cloud-to-butt-revolutionized)
The classic cloud-to-butt Chrome extension, migrated to Manifest V3 and submitted to the Chrome Web Store. The internet deserves more stupid, joyful things. This is mine.

---

## Technical Areas

| Area | What I use it for |
|------|-------------------|
| **Languages** | Python, Rust, Go, TypeScript, Swift, JavaScript |
| **CV / ML** | YOLO (Ultralytics), CoreML, Apple Neural Engine, Roboflow |
| **Systems** | QUIC, libp2p, Kademlia DHT, NAT traversal, CBOR |
| **Cryptography** | ML-DSA-65 (FIPS 204), ML-KEM-768, X25519MLKEM768, UCAN |
| **Edge** | Apple Silicon (M4), CoreML, ANE, Arducam |
| **Native macOS** | Swift, SwiftUI, CoreGraphics, Property Lists |
| **Tooling / CI** | Cargo, Go modules, pip lockfiles, GitHub Actions, Mermaid |

---

## How I Work

**Design before implementation.** AAFP has a NORTH_STAR, eleven RFCs, and a ROADMAP before the crates. "Read this first before any planning or execution."

**Implement twice to validate the spec.** The Go implementation was written from the RFCs without referencing the Rust source, then checked byte-for-byte. If two independent implementations agree, the spec is real.

**Benchmark and label.** DHT scale tests run 10–500 nodes. Load tests run 100 agents and 399K messages. Heuristics are labeled as estimates. Status tables say *Complete* or *Pending*, not "mostly done."

**Document decisions, not just code.** Every project keeps living docs — an engineering logbook, a strategic vision, a handoff file. When I pivot (YOLO11 → YOLO26x), the reason goes in the log.

**Tests are the unit of progress.** Commit messages carry test counts. "1864 tests, 0 failures" is the milestone, not "feature done."

**Iterate in the open and rebase hard.** I force-push history when the narrative changes, because a clean story matters more than a preserved one.

---

## Closing

I'm 17, finishing NVIDIA certification, and starting a gap year late 2026. I'm looking for engineering work in computer vision, edge ML, or developer tools — places where the system has to be right against real hardware or a real spec, not just right in a notebook.

[GitHub](https://github.com/davidnichols-ops) · [X](https://x.com/real_dnichols)
