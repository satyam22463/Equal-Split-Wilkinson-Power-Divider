# 2 GHz Equal-Split Wilkinson Power Divider

A compact microstrip Wilkinson Power Divider designed for 2.0 GHz, simulated in CST Microwave Studio. Uses curved λ/4 branches to reduce board footprint while maintaining clean equal-power splitting and high port isolation.

---

## Key Results

| Parameter | Value |
|---|---|
| Resonant Frequency | 2.02 GHz |
| Input Return Loss $S_{11}$ | −29.13 dB |
| Power Split $S_{21}$ / $S_{31}$ | −3.65 dB (equal) |
| Output Isolation $S_{23}$ | −22.5 dB |
| Harmonic Match | −29.95 dB at 6.04 GHz |

---

## Layout

![3D Layout](figures/layout_3d.png)

> Curved λ/4 branches transition from a 50 Ω input to two 70.7 Ω arms. A lumped 100 Ω resistor bridges the output terminals for isolation.

---

## S-Parameter Response

![S-Parameters](figures/sparams_plot.png)

- **$S_{11}$** — deep null at 2.02 GHz (−29.13 dB), harmonic null at 6.04 GHz
- **$S_{21}$ / $S_{31}$** — balanced −3.65 dB split across both outputs
- **$S_{23}$** — −22.5 dB isolation; leakage absorbed by the 100 Ω resistor

---

## Electric Field Distribution

![E-Field](figures/efield.png)

Symmetric field magnitude across both branches confirms equal in-phase power split. Zero potential difference at the resistor terminals means no current flows through it during matched operation.

---

## Design Equations

**Branch impedance:**
$$Z_{\text{branch}} = \sqrt{2} \cdot Z_0 \approx 70.71\ \Omega$$

**Isolation resistor:**
$$R = 2 \cdot Z_0 = 100\ \Omega$$

**Quarter-wave branch length:**
$$\theta = \frac{\pi}{2}\ \text{rad} \quad \Longrightarrow \quad l = \frac{\lambda_g}{4}$$

---

## Stack

- **Simulation:** CST Microwave Studio (full-wave 3D)
- **Feed:** 50 Ω microstrip, edge-launched SMA
- **Isolation:** Lumped 100 Ω resistor

---

## Files

```
├── wilkinson_divider.tex    # Full LaTeX report
├── cst/                     # CST project files
└── figures/
    ├── layout_3d.png
    ├── sparams_plot.png
    └── efield.png
```
