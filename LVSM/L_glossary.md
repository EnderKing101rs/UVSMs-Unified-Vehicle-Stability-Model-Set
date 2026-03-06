LVSM Glossary: Land Vehicle Stability Model
​The LVSM calculates the Stability Index (S) for land-based systems by weighing the machine's restoring forces against environmental, human, and structural penalties.
​The Master Equation (Land)

$$S_{Land} = \underbrace{\left[ \frac{v^2 \sin(\theta + \beta)}{g R_{turn}} + \frac{I_w \omega \Omega}{mg h_H} \right]}_{\text{Restoring}} + \underbrace{\left[ \eta \sqrt{\mu^2 - (a/g)^2} \right]}_{\text{Buffer}} - \underbrace{\left[ \sin\theta + \frac{F_W}{mg} \right]}_{\text{Toppling}} - \underbrace{k \left[ \frac{\Delta x + \tau \dot{\Delta x}}{h_H} \right]}_{\text{Penalty}} - \underbrace{\left[ \frac{K_{flex} \delta^2}{2mg h_H} \right]}_{\text{Shock}}$$

Variable Definitions
1. Kinetic Restoring (The Machine's Will to Live)
v: Velocity. The primary kinetic energy source for stability.
R_{turn}: Turn radius.
\beta: Road Camber. The surface angle contributing to or detracting from cornering force.
I_w \omega \Omega: Gyroscopic Torque. The product of the wheel's moment of inertia, spin rate, and precession rate.
mg h_H: Gravitational Tipping Moment. The baseline energy required to tip the center of gravity over the pivot point.
2. Stability Buffer (The Grip Budget)
\eta: Surface Fidelity. A multiplier (0 to 1) representing road quality (e.g., gravel vs. asphalt).
\mu: Friction Coefficient. The maximum traction available (Kamm's Circle).
a/g: Longitudinal Load. The ratio of acceleration/braking force to gravity, determining grip usage.
3. Toppling Forces (The External Enemy)
\theta: Lean Angle. The system's deviation from the vertical axis.
F_W: Lateral Wind/Force. External environmental pressure attempting to break frame cohesion.
4. System Penalty (The Human/Lag Factor)
\Delta x: Horizontal Drift. The physical displacement of Frame B (passenger/payload) relative to Frame A (machine).
\tau: Physiological Reaction Lag. The time delay in the passenger's corrective center-of-mass shift.
h_H: Pivot Height. The distance between the center of mass and the ground contact.
5. Elastic Shock (The "High-Side" Variable)
K_{flex}: Frame/Chassis Rigidity.
\delta: Deformation. The displacement of the frame storing potential energy before a snap-back event.
