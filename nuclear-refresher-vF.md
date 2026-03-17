# Nuclear Physics Refresher and Conceptual Micro-Reactor Housing Specification

*Educational summary and theoretical design document — 5 pages*

## 1. Atomic and Nuclear Structure

An atom consists of a dense central nucleus surrounded by a cloud of electrons.  
The nucleus is composed of:

- **Protons** — charge \( +1e \), rest mass \( m_p \approx 1.007825 \, \mathrm{u} \)
- **Neutrons** — charge \( 0 \), rest mass \( m_n \approx 1.008665 \, \mathrm{u} \)

where \( e \) is the elementary charge and \( \mathrm{u} \) is the unified atomic mass unit (\( 1 \, \mathrm{u} = 931.494 \, \mathrm{MeV}/c^2 \)).

Key definitions:

- Atomic number: \( Z \) = number of protons  
- Neutron number: \( N \)  
- Mass number: \( A = Z + N \)

Nuclear radius (approximate):  
\[
R \approx r_0 A^{1/3}, \quad r_0 \approx 1.2 \times 10^{-15} \, \mathrm{m}
\]

Nuclei are bound by the strong nuclear force, which dominates over the Coulomb repulsion between protons at nuclear distances.

## 2. Nuclear Stability, Mass Defect, and Binding Energy

The **binding energy** \( B \) of a nucleus is the energy required to separate it into its individual protons and neutrons.

The **mass defect** \( \Delta m \) is calculated as:

\[
\Delta m = Z m_p + (A - Z) m_n - m_\mathrm{atom}
\]

where:
- \( m_p \) = proton mass  
- \( m_n \) = neutron mass  
- \( m_\mathrm{atom} \) = measured atomic mass (includes electrons)  
- All masses in atomic mass units (\( \mathrm{u} \))

The binding energy is then:

\[
B = \Delta m \times 931.494 \, \mathrm{MeV/u}
\]

(or equivalently \( B = \Delta m \, c^2 \), where \( c \) is the speed of light).

The **binding energy per nucleon** \( B/A \) reaches a maximum near \( ^{56}\mathrm{Fe} \) (\( \approx 8.79 \, \mathrm{MeV/nucleon} \)).  
This peak explains why both **fission of heavy nuclei** and **fusion of light nuclei** are exothermic processes.

## 3. Nuclear Fission and Chain Reactions

Thermal-neutron-induced fission of \( ^{235}\mathrm{U} \) (example):

\[
{}^{235}_{92}\mathrm{U} + {}^1_0\mathrm{n} \rightarrow {}^{236}_{92}\mathrm{U}^* \rightarrow \mathrm{FF}_1 + \mathrm{FF}_2 + \nu \, {}^1_0\mathrm{n} + \gamma + Q
\]

where:
- \( \mathrm{FF}_1, \mathrm{FF}_2 \) = fission fragments (typical: mass ~95 and ~140)  
- \( \nu \) = average number of prompt neutrons released (\( \approx 2.43 \) for \( ^{235}\mathrm{U} \))  
- \( Q \approx 200 \, \mathrm{MeV} \) (total recoverable energy per fission)

Energy partition (approximate):
- ~168 MeV — kinetic energy of fission fragments  
- ~5–7 MeV — prompt neutrons  
- ~7 MeV — prompt γ-rays  
- ~12–15 MeV — delayed β⁻, ν̅_e, and γ from decay products

A self-sustaining chain reaction requires the effective neutron multiplication factor:

\[
k_\mathrm{eff} \geq 1 \quad \text{(criticality condition)}
\]

Thermal reactors use moderators to reduce neutron energy from ~2 MeV to ~0.025 eV, greatly increasing fission cross-sections.

## 4. Thermal Energy Transfer Mechanisms in Nuclear Reactors

Fission energy is deposited primarily as kinetic energy of fission fragments, which is rapidly thermalized into lattice vibrations (heat).

Principal heat transfer modes in the core:

1. **Conduction** — within fuel pellets, through cladding  
2. **Convection** — forced convection in primary coolant (light water, heavy water, liquid metal, gas)  
3. **Thermal radiation** — negligible at normal operating temperatures (< 10% of total)

Typical PWR heat transport path:

Fuel pellet → Zircaloy cladding → primary coolant → steam generator → secondary steam → turbine → generator

Thermal-to-electric efficiency: 33–40% (Rankine cycle limitation).

Core safety limits include:
- Fuel centerline temperature < ~2800 °C  
- Cladding surface temperature < ~1200–1400 °C (to avoid Zr–H₂O reaction)

## 5. Mass–Energy Conversion and Power Scaling

All nuclear energy release derives from Einstein’s mass-energy equivalence:

\[
E = \Delta m \, c^2
\]

For \( ^{235}\mathrm{U} \) thermal fission, typical mass defect per event:

\[
\Delta m \approx 0.215 \, \mathrm{u} \quad \Rightarrow \quad E \approx 200 \, \mathrm{MeV}
\]

Practical equivalence:

1 g of \( ^{235}\mathrm{U} \) fully fissioned produces approximately:

\[
1 \, \mathrm{g} \rightarrow 1 \, \mathrm{MW \cdot day (thermal)} \quad (\approx 8.64 \times 10^{10} \, \mathrm{J})
\]

Conversion pathway (conventional reactors):

Nuclear binding energy release → heat → mechanical work → electrical power

**Conceptual 10 kWth Micro-Reactor Housing Specification**

**Geometry**: Right circular cylinder, total height ≈ 70 cm (including margins)

**Layered radial structure** (inside → outside):

1. **Inner aluminum pressure/structural vessel** (6061-T6 alloy)  
   - Inner diameter: 35 cm  
   - Wall thickness: 5 cm  
   - Functions: structural support, primary coolant channels, low neutron absorption

2. **Tungsten gamma/neutron shielding layer** (W–Ni–Fe alloy, 90–95% W)  
   - Thickness: 10 cm  
   - Provides >10⁴ attenuation for 1–3 MeV gamma rays  
   - High melting point (3422 °C) for passive safety margin

3. **Outer aluminum protective shell** (6061-T6)  
   - Thickness: 2 cm  
   - Optional external cooling fins

**Estimated total dimensions and mass**:
- Outer diameter: ≈ 69 cm  
- Total mass: ≈ 1.2–1.5 metric tons (dominated by tungsten)

**Material properties (selected)**:

| Material          | Density (g/cm³) | Thermal conductivity (W/m·K) | Melting point (°C) | Notes                          |
|-------------------|-----------------|-------------------------------|---------------------|--------------------------------|
| Al 6061-T6        | 2.70            | 167                           | ~660                | Low activation, corrosion resistant |
| W alloy (90–95%)  | 19.25           | 174                           | 3422                | High-density gamma shield      |

*This is a theoretical/educational concept only. Real nuclear systems require licensing, detailed neutronics, thermal-hydraulics, and safety analysis.*

*End of document*
