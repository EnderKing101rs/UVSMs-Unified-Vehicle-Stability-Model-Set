FVSM Glossary: Fluid Vehicle Stability Model
The FVSM calculates the Stability Index (S) for maritime and hydrofoil systems. It focuses on the interface between water and air, where stability is governed by buoyancy and the physical limits of fluid cohesion (cavitation).
The Master Equation (Fluid)

$$S_{Fluid} = \underbrace{\left[ \frac{\overline{GM} \sin\phi}{B} + \frac{F_b}{mg} \right]}_{\text{Restoring}} + \underbrace{\left[ \eta (\sigma) \right]}_{\text{Buffer}} - \underbrace{\left[ \sin\phi + \frac{F_{wave}}{mg} \right]}_{\text{Toppling}} - \underbrace{k \left[ \frac{\Delta x_{load} + \tau \dot{\Delta x}}{h_{meta}} \right]}_{\text{Penalty}} - \underbrace{\left[ \frac{K_{hull} \epsilon^2}{2mg h_{meta}} \right]}_{\text{Shock}}$$

Variable Definitions
1. Buoyant Restoring (The Machine's Will to Float)
\overline{GM}: Metacentric Height. The distance between the Center of Gravity and the Metacenter; the primary lever for vessel stability.
B: Beam Width. The width of the hull, used to scale the metacentric lever.
F_b: Buoyant Force. The upward force of displaced water.
2. Cavitation Buffer (The Grip on the Fluid)
\sigma: Cavitation Number. A dimensionless value representing the margin before water vaporizes (boils) around the hull or foil, causing a loss of "grip."
\eta: Sea State Fidelity. A multiplier (0 to 1) representing water aeration and chop.
3. Toppling Forces (The Maritime Environment)
\phi: Heel/List Angle. The vessel's lean relative to the water's surface.
F_{wave}: Wave Impact Force. External pressure from moving water hitting the hull.
4. Ballast Penalty (The Payload/Crew Factor)
\Delta x_{load}: Load Shift. Horizontal movement of cargo, ballast, or passengers (Frame B) relative to the hull (Frame A).
\tau: Operator Reaction Lag. The delay in adjusting steering or ballast to compensate for a roll.
h_{meta}: Metacentric Pivot Height. The distance from the center of gravity to the metacenter.
5. Slamming Shock (The Structural Limit)
K_{hull}: Hull Rigidity. The resistance of the vessel's structure to deformation.
\epsilon: Hull Deflection. The stored energy during a "slamming" event against the water's surface.
