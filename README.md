# Resonant-Galaxy-Core
Interactive browser simulation of **nested tori** with a GPU particle field, inspired by the Veyra–Barandes resonance framework. Runs entirely client‑side using **WebGPU** (no server required).

**File:** `Resonant-Galaxy-Core.html`

---

## ✨ What it demonstrates
- **Nested torus geometry**: configurable major/minor radii and depth (number of layers).
- **GPU particle dynamics**: simple update rule (compute shader) with inflow/outflow, lensing‑like asymmetry, optional “cogwheel” energy transfer and phase shifting.
- **Observer tilt & multi‑torus layout**: rotate the system; spawn multiple tori around a ring.
- **JWST‑like overlay (mock)**: optional, decorative point set rendered as a separate pass.
- **Performance HUD**: live **FPS** and **active particle count**.
- **State I/O**: save current parameters + particle buffer to JSON; load them back later.
- **Compact, single‑file demo**: no external assets or build tooling needed.

> **Note on data**: the JWST overlay in this demo is **mock/illustrative** (small inline list). It is not a sky‑accurate catalog and should not be used for quantitative analysis.

---

## 🧭 UI & Controls
Left sidebar contains all controls. A **Collapse UI** button toggles the panel.

### Sliders
- **Torus Major Radius** `R`
- **Torus Minor Radius** `r`
- **Nesting Depth** `depth`
- **Particle Count** `n`
- **Outflow Speed** `β` (beta)
- **Throat Compactness** `Ξ` (xi)
- **Strong‑Field Boost** `α_g` (alpha_g)
- **Inflow Slope** `η−δ` (slope)
- **Frame‑Dragging** `ε_fd` (eps_fd)
- **Number of Tori** `numTori`
- **Tilt (rad)** `tilt`

### Toggles
- **Cogwheel Coupling** `cogwheel` (energy transfer between layers)
- **Phase Shifting** `phase_shift` (phase‑dependent distortion)
- **Neural Mode** `neural` (time‑varying color modulation bands)
- **JWST‑like points (mock)** `jwst`

### Save/Load
- **Save State** → downloads `tgp_state.json` with current params + first `n` particles.
- **Load State** → choose a previously saved JSON to restore parameters and particles.

---

## 🚀 Run Instructions

### Option A — Open directly (simplest)
1. Ensure you have a **WebGPU‑capable browser** (see below).
2. Double‑click `Resonant-Galaxy-Core.html` to open it.
3. If your browser blocks WebGPU from file URLs, use Option B.

### Option B — Serve locally (recommended)
Any static server works; here’s a Python example:
```bash
# From the directory containing the HTML
python -m http.server 8080
# Then visit:
# http://localhost:8080/Resonant%20-%Galaxy-%20Core.html
```

---

## 🌐 Browser Compatibility (WebGPU)
- **Chrome 113+ / Edge 113+** — WebGPU enabled by default on most desktop GPUs.
- **Firefox (Nightly/Dev)** — may require enabling WebGPU in about:config.
- If you see **“WebGPU not supported / No adapter found”** in the app:
  - Update your browser & GPU driver.
  - Try launching Chrome/Edge with `--enable-unsafe-webgpu` (older systems).
  - Switch to a machine with a newer GPU/OS combo.

---

## 🛠️ Tips & Performance
- Start with moderate **Particle Count** (`n` = 10k–50k). Increase gradually.
- Use **Collapse UI** to maximize canvas area.
- For multiple tori, consider reducing `n` to keep frame‑rate smooth.
- Saving state includes only the first `n` particles; re‑load the same `n` for a consistent preview.

---

## 📄 License & Attribution
- This demo HTML lists styles and shaders inline for portability.
- JWST overlay here is **mock**; it is included for visual context only.

