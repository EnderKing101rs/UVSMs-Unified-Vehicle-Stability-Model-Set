# LVSM Glossary: Land Vehicle Stability Model

The **LVSM** calculates the Stability Index ($S$) for land-based systems by weighing the machine's restoring forces against environmental and human penalties.

## The Master Equation (Land)

$$S_{Land} = \underbrace{\left[ \frac{v^2 \sin(\theta + \beta)}{g R_{turn}} + \frac{\Gamma}{R_w^2} \right]}_{\text{Restoring}} + \underbrace{\left[ \eta \sqrt{\mu^2 - (a/g)^2} \right]}_{\text{Buffer}} - \underbrace{\left[ \sin\theta + \frac{F_W}{mg} \right]}_{\text{Toppling}} - \underbrace{k \left[ \frac{\Delta x + \tau \dot{\Delta x}}{h_H} \right]}_{\text{Penalty}} - \underbrace{\left[ \frac{K_{flex} \delta^2}{2mg} \right]}_{\text{Shock}}$$

---

## Variable Definitions

### 1. Kinetic Restoring (The Machine's Will to Live)
* **$v$**: Velocity. The primary energy source for stability.
* **$R_{turn}$**: Turn radius.
* **$\beta$**: Road Camber. The "help" or "hindrance" provided by the surface angle.
* **$\Gamma$**: Gyroscopic Coefficient. The stabilizing force of spinning wheels.

### 2. Stability Buffer (The Grip Budget)
* **$\eta$**: Surface Fidelity. A multiplier (0 to 1) representing road quality (gravel vs. asphalt).
* **$\mu$**: Friction Coefficient. The maximum traction available (Kamm's Circle).
* **$a/g$**: Longitudinal Load. How much "grip" is being used by braking or accelerating.

### 3. Toppling Forces (The External Enemy)
* **$\theta$**: Lean Angle. The deviation from the vertical axis.
* **$F_W$**: Lateral Wind/Force. External pressure trying to break the frame cohesion.

### 4. System Penalty (The Human/Lag Factor)
* **$\Delta x$**: Horizontal Drift. The physical displacement of the passenger/payload.
* **$\tau$**: Physiological Reaction Lag. The time delay in the passenger's corrective movement.
* **$h_H$**: Pivot Height. The distance between the center of mass and the ground contact.

### 5. Elastic Shock (The "High-Side" Variable)
* **$K_{flex}$**: Frame/Chassis Rigidity. 
* **$\delta$**: Deformation. The amount of "stored energy" in the frame before a snap-back.