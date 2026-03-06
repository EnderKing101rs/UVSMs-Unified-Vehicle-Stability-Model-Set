# FVSM Glossary: Fluid Vehicle Stability Model

The **FVSM** calculates the Stability Index ($S$) for maritime and hydrofoil systems, where the "Grip Budget" is defined by cavitation and buoyancy.

## The Master Equation (Fluid)

$$S_{Sea} = \underbrace{\left[ \overline{GM} \sin\phi + V_{disp} \right]}_{\text{Restoring}} + \underbrace{\left[ \eta (P_{cav} - P_{local}) \right]}_{\text{Buffer}} - \underbrace{\left[ \sin\phi + \frac{F_{wave}}{mg} \right]}_{\text{Toppling}} - \underbrace{k \left[ \frac{\Delta x_{load} + \tau \dot{\Delta x}}{h_{meta}} \right]}_{\text{Penalty}} - \underbrace{\left[ \frac{K_{hull} \epsilon^2}{2mg} \right]}_{\text{Shock}}$$

---

## Variable Definitions

### 1. Buoyant Restoring (The Machine's Will to Float)
* **$\overline{GM}$**: Metacentric Height. The distance between the Center of Gravity and the Metacenter; the primary lever for upright stability.
* **$V_{disp}$**: Displacement Volume. The physical "Frame" of water displaced by the hull.

### 2. Cavitation Buffer (The Grip on the Fluid)
* **$P_{cav}$**: Vapor Pressure. The physical limit where water boils into steam around a foil.
* **$P_{local}$**: Local Pressure. The actual pressure exerted on the hull or foil.
* **$\eta$**: Surface Fidelity. Accounts for aeration or "choppy" water state.

### 3. Toppling Forces (The Fluid Environment)
* **$F_{wave}$**: Impact force of waves attempting to break the system's equilibrium.

### 4. Ballast Penalty (The Payload/Crew Factor)
* **$\Delta x_{load}$**: Cargo or Crew Shift. The horizontal movement of Frame B (The Payload) relative to Frame A (The Hull).
* **$\tau$**: Operator Reaction Lag. The delay in adjusting ballast or steering to compensate for a roll.

### 5. Slamming Shock (The Structural Limit)
* **$K_{hull}$**: Structural Rigidity of the Hull.
* **$\epsilon$**: Hull Deflection. The energy stored and released when a hull "slams" against an incompressible fluid surface.
