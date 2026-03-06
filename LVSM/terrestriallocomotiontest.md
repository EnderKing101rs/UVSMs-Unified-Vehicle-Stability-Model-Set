## Definitive Terrestrial Transportation Stability Equation (UVSM - Land)

The unified stability metric \( S \) for any land-based transportation system (bikes, cars, tanks, trains, legged creatures, etc.) is given by:

$$S = \underbrace{\left[ \frac{v^{2} \sin(\theta + \beta)}{g R_{turn}(\theta, \delta, L_{eff})} + \frac{\Gamma}{R_{w}^{2}} \right]}_{\text{Kinetic Restoring}} + \underbrace{\left[ \eta \sqrt{\mu^{2} - \left( \frac{a}{g} \right)^{2}} \cdot \frac{(mg \cos\theta + F_{DF}) \cdot (1 + K_{roll} \cdot \phi)}{mg} \right]}_{\text{Dynamic Traction Buffer}} - \underbrace{\left[ \sin\theta \left(1 + \frac{y_{cp}}{h_{CoM}}\right) + \frac{F_{W}}{mg} \right]}_{\text{Toppling \text{ } Environment}} - \underbrace{k_{eff}(a) \left[ \frac{\Delta x_{GH} + \tau \Delta \dot{x}}{h_{H}} \right]}_{\text{Passenger / System Penalty}} - \underbrace{\left[ \frac{K_{flex} \delta^{2} + K_{susp} \delta_{susp}^{2}}{2mg} \right]}_{\text{Elastic Shock}} - \underbrace{\left[ \begin{matrix} \text{legged: } K_{leg} (f_{leg} - f_{opt})^{2} \\ \text{tracked: } K_{shear} (slip\_ratio)^{2} \\ \text{railed: } K_{flange} (y_{flange}/gauge)^{2} \\ \text{wheeled: } 0 \end{matrix} \right]}_{\text{Locomotion Penalty}}$$

$S > 0 \rightarrow$ Frame C locked (stable)  
$S \leq 0 \rightarrow$ Frame Separation Event (crash / loss of control / derailment / slip / stumble)

### Degeneration Rules (Quick Reference)
- **Bike / Motorcycle**: legged_mode = tracked_mode = railed_mode = 0, δ = 0, K_roll = 0, K_susp = 0  
- **Street / Off-road Car**: θ = 0, δ active, legged_mode = tracked_mode = railed_mode = 0  
- **Tank / Tracked**: tracked_mode = 1, δ = differential track speed, θ = 0, μ → soil shear  
- **Train**: railed_mode = 1, δ = 0, y_flange → flange clearance  
- **Insect / Legged**: legged_mode = 1, other modes = 0, f_leg = stride frequency

All terms are dimensionally homogeneous (S is dimensionless).  
The equation reduces to the original clean GitHub bike form when wheeled-specific terms are zeroed.
