# Space-Deployable Micro-Reactor (Space SMR)  
## Powering an Orbital AI Data Center with Nvidia Vera Rubin Space Module

**Conceptual Engineering Blueprint – March 2026**  
*Grounded in NASA Fission Surface Power (FSP), DARPA DRACO/Kilopower heritage, Westinghouse/Lockheed Martin contracts, and Nvidia GTC 2026 announcements*

No commercial system exists today. This is a realistic 8–10 year, multi-billion-dollar sovereign-level project requiring DOE, NRC, NASA, FAA, ITAR, and UN Outer Space Treaty compliance.

## Objective
Build and launch a compact fission micro-reactor (40–120 kWe) to provide reliable baseload power for an orbital AI data center using Nvidia’s **Vera Rubin Space Module** (radiation-hardened GPU/CPU platform).  
The reactor must survive launch on **SpaceX Starship**, operate in vacuum, shield electronics, and enable laser downlink of training data to Earth response centers.

## Global Critical Minerals Sourcing Map
![Global Critical Minerals Sourcing Map](map.png){ width=100% }

## Phase 1 – Material Sourcing (6–12 months)

| Material              | Primary Role                          | Top Producing Nations (2025–2026)                  | Key Locations / Notes                              |
|-----------------------|---------------------------------------|----------------------------------------------------|----------------------------------------------------|
| **Uranium**           | Fissile fuel base ($^{235}U$, $UO_2$, UN, U-Zr) | **Kazakhstan** (39–43%), **Canada** (24%), Namibia (12%) | Inkai (Kaz), Athabasca Basin (Can), Husab (Nam)   |
| **Zirconium**         | Cladding, low-absorption alloys       | **Australia** (#1 zircon), **South Africa** (#2)   | Iluka/Rio Tinto (Aus), Richards Bay (SA)           |
| **Beryllium**         | Neutron reflector + shielding (BeO)   | **United States** (~60–80%)                        | Spor Mountain, Utah (Materion)                     |
| **Lithium**           | LiH neutron shielding, possible fluids| **Australia**, **China**, Chile/Argentina          | Greenbushes (Aus), Salar de Atacama (Chile)        |

**Travel itinerary**: Kazakhstan → Canada → Namibia → Australia → South Africa → United States (Utah).

## Phase 2 – Fuel Fabrication & Enrichment (12–24 months)

1. Convert yellowcake → $UF_6$
2. Enrich to HEU/HALEU (critical for small-core criticality due to neutron leakage)
   - Physics equation:  
     $$ k_{\text{eff}} = k_{\infty} \times P_{\text{non-leakage}} $$
3. Fabricate pins/pellets (Westinghouse, DOE labs, Framatome, or Rosatom)

**Bottleneck**: Civilian HEU/HALEU capacity still limited in 2026

## Phase 3 – Core Physics Design & Validation (18–36 months)

**Key physics equations**

- Fission energy release:  
  $$ ^{235}\text{U} + n \rightarrow \text{fission products} + \sim 2.4\,n + \sim 200\,\text{MeV} $$

- One-group diffusion (approximation):  
  $$ D \nabla^2 \phi - \Sigma_a \phi + \nu \Sigma_f \phi = 0 $$

- Radiative heat rejection (space):  
  $$ P = \epsilon \sigma A T^4 $$  
  ($\epsilon \approx 0.8$–$0.9$, $T \approx 800$–$1000$ K radiator temperature)

**Validation steps**:
- Monte Carlo neutronics (MCNP, Serpent)
- Non-nuclear heat-pipe testing (NASA Glenn)
- Nuclear ground test (Nevada or Idaho National Lab)
- Cold critical experiment

## Phase 4 – Shielding, Structure & Assembly

- **Neutron shield**: Beryllium reflector + $^7$LiH
- **Gamma shield**: Tungsten or depleted uranium
- **Structure**: Ti alloys, carbon composites
- **Total shielding goal**: Keep Vera Rubin dose <10 krad/year

**Assembly location**: Certified US cleanroom (INL, Marshall Space Flight Center, or contractor facility)

## Phase 5 – Power Conversion & Nvidia Integration

- **Power output**: 40–120 kWe DC
- **Conversion**: Stirling cycle (preferred) or thermoelectric
- **Interface**: Power conditioning unit → Vera Rubin rack bus
- **Radiation tolerance**: Vera Rubin already hardened; add local shielding

## Phase 6 – Satellite Bus Integration

- Deployable radiators (large area for heat rejection)
- Attitude control (reaction wheels/CMGs)
- Communications: Laser downlink (high-bandwidth training data)
- **Total spacecraft mass**: ~10–15 tonnes

## Phase 7 – Launch on SpaceX Starship

- **Vehicle**: Starship (Super Heavy) – >100 t to LEO
- **Launch sites**: KSC LC-39A (Florida) or Starbase (Texas)
- **Regulatory path** (2026):
  - FAA payload license
  - DOE/NRC nuclear safety analysis (launch accident prob. < $10^{-6}$)
  - NASA/DoE certification
  - Environmental Impact Statement
  - ITAR/State Dept approval

## Phase 8 – Orbital Operations

1. Launch to LEO parking orbit
2. Deploy radiators & solar arrays (initial power)
3. Reactor startup (neutron source or rod withdrawal)
4. Vera Rubin Space Module activation
5. On-orbit AI training/inference
6. Downlink processed data via optical/laser link to Earth stations

**Design lifetime**: 10+ years (replaceable units)

## Major Bottlenecks (2026 Reality Check)

1. HEU/HALEU supply chain & export controls
2. Nuclear launch safety certification (multi-year)
3. Mass budget vs. shielding requirements
4. International Outer Space Treaty compliance
5. Cost ($1–5B+) and timeline (first demo likely 2032–2035)

**Bottom line**  
This is technically feasible using demonstrated physics and near-term hardware, but it is a nation-state or large-consortium project — not a private garage build.

**Prepared by Grok – March 2026**

## Appendix C: In-Depth Physics of Small Modular Reactors (SMRs)

### C.1 Nuclear Chain Reaction & Criticality

The core principle is a self-sustaining fission chain reaction where each fission produces enough neutrons to cause exactly one more fission on average (k_eff = 1).

**Six-factor formula** (infinite multiplication factor k_∞):
$$ k_{\infty} = \eta \times \epsilon \times p \times f $$
- $\eta$: neutrons produced per absorption in fuel (~2.4 for $^{235}$U thermal)
- $\epsilon$: fast fission factor (~1.02–1.05)
- $p$: resonance escape probability (~0.85–0.95)
- $f$: thermal utilization (~0.9–0.95)

For finite small cores (typical SMR size):
$$ k_{\text{eff}} = k_{\infty} \times P_{\text{NL}} $$
$P_{\text{NL}}$ (non-leakage probability) drops sharply due to high surface-to-volume ratio → requires higher enrichment (HALEU 5–20% or HEU >19.75%).

**Criticality condition**:
$$ k_{\text{eff}} = 1 \quad \Rightarrow \quad \text{steady power} $$
$$ k_{\text{eff}} > 1 \quad \Rightarrow \quad \text{supercritical (power rise)} $$
$$ k_{\text{eff}} < 1 \quad \Rightarrow \quad \text{subcritical (power decay)} $$

### C.2 Neutron Diffusion & Flux Distribution

In steady-state, neutron balance is governed by the diffusion equation (Fick’s law approximation):
$$ -D \nabla^2 \phi(\mathbf{r}) + \Sigma_a(\mathbf{r}) \phi(\mathbf{r}) = \nu \Sigma_f(\mathbf{r}) \phi(\mathbf{r}) + S(\mathbf{r}) $$
For critical reactor (S = 0, one-group):
$$ \nabla^2 \phi + B^2 \phi = 0 $$
where $B^2 = (\nu \Sigma_f - \Sigma_a)/D$ is the material buckling.

In small SMR cores, flux peaks centrally and leaks strongly at edges → requires reflectors (Be, graphite) to reduce leakage.

### C.3 Reactivity Feedback Mechanisms (Passive Safety)

All modern SMRs rely on inherent negative feedback:

1. **Doppler broadening** (fuel temperature coefficient)  
   Resonance absorption in $^{238}$U increases with temperature → negative $\alpha_D \approx -1$ to $-3$ pcm/K

2. **Moderator temperature coefficient** (MTC)  
   Water density decreases with temperature → reduced moderation → negative in thermal-spectrum LWR-SMRs

3. **Void coefficient**  
   Boiling or gas voids reduce moderation → negative in most designs

4. **Power coefficient**  
   Combined effect: $\alpha_P < 0$ → power excursion self-limits

For space SMRs: heat-pipe designs are conduction/radiation-limited → strong negative temperature feedback from expansion and spectrum shift.

### C.4 Heat Transfer & Removal in Vacuum

Fission heat (~200 MeV/fission → ~0.033 pJ/fission) must be rejected by radiation only:
$$ P_{\text{reject}} = \epsilon \sigma A (T^4 - T_{\text{env}}^4) \approx \epsilon \sigma A T^4 $$
( $T_{\text{env}} \approx 3$ K negligible)

Example: 100 kWt thermal → ~70 kW reject at $\epsilon=0.85$, $T=900$ K → $A \approx 5.5$ m² (deployable panels).

Heat pipes (sodium/potassium wick) transport heat passively in zero-g via capillary action and vaporization/condensation cycle.

### C.5 Radiation Damage & Fuel Lifetime

Neutron fluence: ~$10^{21}$–$10^{22}$ n/cm² over life  
Effects:
- Swelling & creep in metallic fuels
- Fission gas release in ceramics
- Embrittlement in cladding

TRISO or UN fuels offer superior retention (used in prismatic HTGR-SMRs).

### C.6 Mass-to-Energy Conversion Summary

Per kg of fully fissioned $^{235}$U:
- Mass defect $\Delta m \approx 1$ g → $E = \Delta m c^2 \approx 9 \times 10^{13}$ J (~25 GWh thermal)
- Practical burnup: 50–100 GWd/tHM → ~4–8% fissioned → still millions of times chemical energy density

This physics enables a ~9-tonne reactor to deliver 50 kWe continuously for 12+ years in orbit — unmatched by any other power source.

**End of Document**
