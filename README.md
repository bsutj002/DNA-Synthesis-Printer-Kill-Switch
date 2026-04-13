# DNA Synthesis Digital Twin (MVM 1.2)

## Project Overview
This project develops a high-fidelity, multi-scale state-space model for a DNA synthesis printer. Its primary purpose is to ensure sequence fidelity and safety during the synthesis of sensitive genetic materials by predicting and verifying process parameters in real-time and to ensure that if necessary, the operation is capable of shutting down immediately.

---

## Accomplishments (MVM 1.1 – 1.2)
I have successfully transitioned the project from a static chemical model to a dynamic, piecewise-continuous simulation. Key technical milestones include:

Hybrid Flow Modeling: I have moved beyond ideal PFR assumptions to implement a Pulse-Wait (Incubation) flow regime using a compartment model consisting of a PFR connected to a batch reactor, which loops back to the PFR via recyle stream. This captures the industrial reality of stop-flow synthesis, where reagent is pulsed into the bed and allowed to incubate under batch conditions to maximize coupling yield.

Mass Transfer & Fluidics: Implemented the Nelson-Galloway correlation for modelling the mass transfer of the reagent passing through a bed of packed beads and integrated Taylor-Aris dispersion to accurately model reagent arrival fronts.

Steric Hindrance & Yield Tracking: Established a "Batch Progress" state ($\zeta$) that accounts for steric hindrance and porosity decay as the DNA chain grows through the addition of phosphoramidite base pairs. The model now successfully tracks 
yield decay across sequential coupling cycles.

Thermal Dynamics: Established a temperature-dependent viscosity and a heat removal term to the energy balance equations to ensure that the heat transfer being depicted in the system is as realistic as possible.

Yield Prediction: I designed the model to predict yield decay over multiple coupling cycles by tracking concentration and temperature trajectories across sequential pulses.
Transient Analysis: Established a foundation for analyzing process fluctuations rather than just steady-state averages.

---

## Future Direction: MVM 1.3
The next phase of my development focuses on **Industrial Realism** and economic optimization:

Sequential Wash Cycles: Implementing a move toward a true time-aligned trajectory (TAT).

Waste State Integration: I will introduce a waste state to quantify reagent loss during arrival front dispersion, transitioning the model from a purely chemical simulation to an economic optimization tool.

---

## Technical Core
The model relies on the following mathematical frameworks:
State-Space Modeling: For multi-scale process tracking.
Chemical Engineering Kinetics: Modeling the underlying synthesis reactions.
Mass Transfer: Leveraging the Nelson-Galloway correlation.
