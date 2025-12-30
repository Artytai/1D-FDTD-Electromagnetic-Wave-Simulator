
# 1D FDTD Electromagnetic Wave Simulator

A browser-based, interactive simulation of electromagnetic wave propagation using the **Finite-Difference Time-Domain (FDTD)** method (1D Yee scheme). The app renders **E-field (Ex)** and **H-field (Hy)** in real time, supports **material interfaces** via εᵣ split, and provides simple **edge damping** (PML-like) to minimize reflections.

> **Live demo:** (add after enabling GitHub Pages)  
> https://YOUR_GITHUB_USERNAME.github.io/1D-FDTD-Electromagnetic-Wave-Simulator/

> **Code:**  
> https://github.com/YOUR_GITHUB_USERNAME/1D-FDTD-Electromagnetic-Wave-Simulator

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

### Option A — Open locally
1. Clone or download the repo.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Click **Play** (or it may auto-start if your version uses auto-run).

### Option B — Host with GitHub Pages
1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (or `master`)
   - **Folder**: `/root`
4. Save. After a minute, your app will be live at:  
   `https://YOUR_GITHUB_USERNAME.github.io/1D-FDTD-Electromagnetic-Wave-Simulator/`
5. Put that link in your submission’s **Live URL** field.

---

## 📁 Project Structure
