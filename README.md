
# 1D FDTD Electromagnetic Wave Simulator

A browser-based, interactive simulation of electromagnetic wave propagation using the **Finite-Difference Time-Domain (FDTD)** method (1D Yee scheme). The app renders **E-field (Ex)** and **H-field (Hy)** in real time, supports **material interfaces** via εᵣ split, and provides simple **edge damping** (PML-like) to minimize reflections.


---

## ✨ Features

- **Interactive controls** for:
  - Grid points `N`, cell size `Δx`, **CFL** factor
  - Source type (**Sine** or **Gaussian pulse**), frequency, amplitude
  - Source index `iₛ`
  - Material split index and relative permittivities **εᵣ(A)** and **εᵣ(B)**
  - Edge absorber width and damping strength
- **Real-time visualization**:
  - Ex (green), Hy (orange)
  - Material boundary (cyan dashed line)
  - Source marker (cyan dot)
- **HUD readout**:
  - `t`, `dt`, `CFL`, `N`, `dx`, `src`, `εᵣ` values
  - **Energy** estimate: ∑(½ ε Ex² + ½ μ Hy²)
- **Controls**:
  - **Apply / Reset** – re-read inputs and reset fields
  - **Play / Pause** – start/stop the time loop
  - **Step once** – advance one time step
  - **Save snapshot** – download PNG of the canvas
  - **Clear fields** – zero the fields
- **Single-file build** – works offline, no external dependencies

---

## 🚀 Quick Start

###  Open locally
1. Clone or download the repo.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Click **Play** (or it may auto-start if your version uses auto-run).

---
## 🎛️ Controls & Parameters

- **Grid points (N)**: number of cells in the 1D grid.
- **Cell size (Δx)**: spatial step in meters.
- **CFL factor**: stability factor; `dt = CFL * Δx / c`. Keep ≤ 1 (typically 0.5–0.95).
- **Source type**: `Sine` or `Gaussian Pulse`.
- **Frequency (Hz)**: sinusoid/pulse frequency.
- **Amplitude**: source amplitude.
- **Source index iₛ**: cell at which the source is injected.
- **Region A εᵣ**, **Region B εᵣ**, **Split index**: define a two-region medium.
- **Absorber width**: number of cells near edges with damping.
- **Edge damping**: damping strength (0–0.2). Higher values reduce reflections more, but can over-damp.

---

## 🧠 Physics Model (Short)

- **Discretization**: 1D **Yee** leapfrog scheme:
  - Update **H** from spatial differences of **E**.
  - Update **E** from spatial differences of **H** using local **ε = ε₀·εᵣ**.
- **Time step**: `dt = CFL · Δx / c` (conservative vacuum limit).
- **Material interface**: set **εᵣ** per cell using the split index.
- **Source**: soft source added to `Ex[iₛ]`, either sinusoidal or Gaussian pulse.
- **Edge damping**: simple quadratic profile at both ends (PML-like), not a full Berenger PML but effective for demos.
- **Energy**: `E_total ≈ Σ(½ ε Ex² + ½ μ₀ Hy²)` used as a diagnostic.

---
## 🙏 Acknowledgments

- Built by Arthur Tai.  
- Thanks to the FDTD/Yee method literature for foundational ideas (discrete-time EM on staggered grids).
