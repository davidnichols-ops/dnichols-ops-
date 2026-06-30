# David Nichols

**Building vision systems that work on real hardware.** 17. Edge-first.

[![X](https://img.shields.io/twitter/follow/real_dnichols?style=social)](https://x.com/real_dnichols)

---

### 🔬 [apple-quality-recognition-engine](https://github.com/davidnichols-ops/apple-quality-recognition-engine)

Real-time CV pipeline for apple variety detection and USDA grading. Built for the family orchard — harvest deadline November 28, 2026.

```
YOLO11 → CoreML → Apple Neural Engine (M4)
Detection: on-device. Grading: deterministic YAML policy. No judgment in the weights.
```

- **6-stage pipeline:** instance parsing → discard check → IoA spatial binding → deterministic grading → edge harvest → output render
- **Hardware-hardened:** automatic Arducam reconnection on frame drop, operator override logging
- **Active learning foundation:** low-confidence frames (0.40–0.65) auto-captured for retraining
- **Dynamic config:** defect taxonomy and facility rules loaded at runtime — change policy without retraining

---

---

### 🧠 Principles

> **Neural networks identify. Algorithms decide.**

Judgment is deterministic, auditable, and lives in config — not floating-point weights. Edge-first means on-device. Hardware reliability is table stakes, not an afterthought. Low-confidence frames are free training data if you capture them from day one.

---

### 📬 Open to roles

Completing NVIDIA certification. Gap year starts late 2026. Looking for engineering work in computer vision, edge ML, or developer tools.

[GitHub](https://github.com/davidnichols-ops) · [X](https://x.com/real_dnichols)

---
