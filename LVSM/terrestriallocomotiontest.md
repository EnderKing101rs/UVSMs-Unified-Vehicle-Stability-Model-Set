# The Universal Vehicle Stability Model ($S_{Uni}$)

### **Overview: The "Physics Engine" Logic Gate**
The Unified Vehicle Stability Model Set (UVSMs) treats reality as a recursive physics engine. It provides a universal, mathematically rigorous logic gate ($S$) that defines the exact threshold of frame cohesion (stability) and frame separation (crashing, stalling, capsizing, or derailing) for any dynamic system. 


$$S \leq 0 \rightarrow \text{Frame Separation Event (Failure)}$$

### **The Master Equation**
This equation dynamically calculates stability across Land, Air, and Fluid mediums, smoothly handling transitions (e.g., a vehicle jumping, a seaplane taking off, or a submarine diving) through Phase Faders ($\Lambda$). Every term resolves to a dimensionless ratio (a percentage of the vehicle's failure threshold) to ensure perfect dimensional homogeneity.

$$
\begin{aligned}
S_{Uni} = &\underbrace{\left[ \Lambda_L \left( \frac{v^{2} \sin(\theta + \beta)}{g R_{turn}} \right) + \Lambda_A \left( \frac{L \cos\phi}{mg} \right) + \Lambda_F \left( \frac{\overline{GM} \sin\phi}{B} \right) + \frac{\Gamma}{R_{w}^{2}} \right]}_{\text{Phase-Weighted Restoring}} \\
&+ \underbrace{\left[ \Lambda_L \left( \eta_L \sqrt{\mu^{2} - \left( \frac{a}{g} \right)^{2}} \cdot \frac{F_{N} + F_{DF}}{mg} \right) + \Lambda_A (\eta_A) + \Lambda_F (\eta_F) \right]}_{\text{Phase-Weighted Buffer}} \\
&- \underbrace{\left[ \sin\theta \left(1 + \frac{y_{cp}}{h_{CoM}}\right) + \frac{F_{W}}{mg} \right]}_{\text{Universal Toppling}} \\
&- \underbrace{k_{eff}(a) \left[ \frac{\Delta x_{GH} + \tau \Delta \dot{x}}{h_{H}} \right]}_{\text{System Penalty}} - \underbrace{\left[ \frac{K_{flex} \delta^{2} + K_{susp} \delta_{susp}^{2}}{2mg h_H} \right]}_{\text{Universal Shock}} \\
&- \underbrace{\left[ \begin{matrix} \text{legged: } K_{leg} \left(\frac{f_{leg} - f_{opt}}{f_{opt}}\right)^{2} \\ \text{tracked: } K_{shear} (R_{slip})^{2} \\ \text{railed: } K_{flange} \left(\frac{y_{flange}}{w_{gauge}}\right)^{2} \\ \text{wheeled: } 0 \end{matrix} \right]}_{\text{Locomotion Penalty}}
\end{aligned}$$

---

### **How It Works: The Phase Faders ($\Lambda$)**
To handle multi-medium transitions, the model uses Phase Faders. These dimensionless multipliers dictate what percentage of the vehicle's weight is currently supported by which medium. In a stable state, they scale from 0 to 1, and always sum to 1 ($\Lambda_L + \Lambda_A + \Lambda_F = 1$). 
* **Jumping/Freefall:** If a land vehicle hits a ramp and goes airborne, $\Lambda_L$ drops to 0. This instantly zeroes out the dynamic traction buffer, leaving the vehicle reliant entirely on gyroscopic restoring forces ($\Gamma$) and vulnerable to aerodynamic toppling.
* **Taking Off/Diving:** As an aircraft accelerates, aerodynamic lift ($L$) increases, smoothly transferring the weight ratio from $\Lambda_L$ to $\Lambda_A$ until the tires leave the runway.

---

### **Universal Variable Glossary**

#### **1. Phase Faders (Medium Support Ratios)**
* **$\Lambda_L$**: Land Support Ratio. The percentage of weight supported by the ground via the Normal Force ($F_N / mg$).
* **$\Lambda_A$**: Air Support Ratio. The percentage of weight supported by aerodynamic lift ($L / mg$).
* **$\Lambda_F$**: Fluid Support Ratio. The percentage of weight supported by buoyancy ($F_b / mg$).

#### **2. Restoring & Buffer Metrics (The Machine's Grip & Will)**
* **$v$**: Velocity. Forward speed of the system.
* **$\theta$**: Pitch/Incline Angle. The slope of the terrain or the vehicle's pitch.
* **$\beta$**: Slip/Bank Angle. The lateral drift or intentional banking of the system.
* **$R_{turn}$**: Turn Radius.
* **$L$**: Aerodynamic Lift Force.
* **$\phi$**: Roll/Heel Angle. The lateral lean of the vehicle.
* **$m$**: Total Mass of the vehicle and payload.
* **$\overline{GM}$**: Metacentric Height. The maritime leverage point for buoyant stability.
* **$B$**: Beam Width. The physical width of the hull or frame.
* **$\Gamma$**: Gyroscopic Restoring Torque. The stabilizing rotational inertia of wheels, rotors, or flywheels.
* **$R_w$**: Wheel or Rotor Radius. Scales the gyroscopic effect.
* **$\eta_L, \eta_A, \eta_F$**: Medium Fidelity Modifiers. Quality scores (0 to 1) for surface integrity, air density, or sea state.
* **$\mu$**: Coefficient of Friction.
* **$a$**: Longitudinal Acceleration/Deceleration. Heavy braking consumes the friction circle, reducing available lateral grip.
* **$F_N$**: Normal Force. The actual physical weight pressing into the ground.
* **$F_{DF}$**: Aerodynamic Downforce. Artificial weight pressing the vehicle into the ground without adding mass.

#### **3. Toppling, Shock & Penalties (The Environment & Hardware Limits)**
* **$y_{cp}$**: Height of the Aerodynamic Center of Pressure. Where external winds apply their leverage.
* **$h_{CoM}$**: Height of the Center of Mass. The physical balance point of the vehicle.
* **$F_W$**: External Environmental Force. Crosswinds, wave impacts, or sudden gusts.
* **$k_{eff}(a)$**: Effective Acceleration Penalty Multiplier. Scales the danger of payload shifts under heavy G-loads.
* **$\Delta x_{GH}$**: Payload/Operator Center of Gravity Migration. The distance internal mass has shifted from neutral.
* **$\tau$**: Operator/System Reaction Lag. The delay (in seconds) before a corrective input is applied.
* **$h_H$**: Gravitational Tipping Moment Height (Pivot Height). Crucial for dimensional normalization.
* **$K_{flex}$ & $K_{susp}$**: Frame and Suspension Stiffness Coefficients.
* **$\delta$ & $\delta_{susp}$**: Frame Deflection and Suspension Travel distances.

#### **4. The Locomotion Penalty Matrix**
A dynamically swapping penalty based on how the machine interacts with the ground, dimensionally normalized to represent a percentage of gait or traction failure.
* **$f_{leg}$ & $f_{opt}$**: Current and Optimal Step Frequencies (Hertz) for legged mechs/exoskeletons.
* **$slip\_ratio$**: Track Slippage Percentage for continuous track vehicles.
* **$y_{flange}$ & $gauge$**: Lateral Flange Shift and Track Gauge width for railed vehicles.
* **$K_{leg}, K_{shear}, K_{flange}$**: Locomotion-specific scaling constants.
