MODEL NAME

Eukaryotic Symbiont – Prokaryotic Host Symbiosis Simulation

1. Purpose of the Model

This simulation models the conceptual evolution of a eukaryotic symbiont
within a prokaryotic host. The primary focus is on the development of
a specialized organelle called "nitroplast" and energy dynamics
arising from interactions between cellular components and environmental factors.

2. Key Concepts and Assumptions

- The symbiont genome is represented as a binary array; gene states
  can mutate randomly.
- Key organelles (mitochondria, chloroplast, ribosome, nitroplast)
  have efficiency values influencing energy production and survival.
- Evolution of nitroplast occurs when its function efficiency exceeds
  a threshold (>0.95).
- The host genome mutates independently with a low probability.
- Environment variables (temperature, pH, toxins, nutrients, light)
  fluctuate slightly each generation.
- Energy production and consumption are simplified abstractions,
  not actual biochemical calculations.

3. Model Logic

The simulation iteratively performs the following per generation:
1. Environment fluctuations affect nutrients, light, and other factors.
2. The prokaryotic host genome undergoes random mutations.
3. The eukaryotic symbiont genome mutates and organelles undergo
   efficiency changes.
4. Symbiont energy level is calculated based on:
   - Production from mitochondria (nutrients) and chloroplast (light)
   - Consumption by all organelles
5. If energy <= 0, the symbiont dies and simulation ends.
6. If nitroplast efficiency exceeds 0.95, it is fully developed and simulation ends.
7. Energy levels and generation count are recorded for analysis.

4. Code Implementation

- **Classes**:
  - `CellularComponent`: Represents organelles with efficiency and mutation logic.
  - `EukaryoticSymbiont`: Contains genome and organelles; handles mutation, metabolism, and nitroplast evolution.
  - `ProkaryoticHost`: Contains genome and mutates independently.
  - `Environment`: Stores environmental variables and applies random fluctuations.
- **Simulation function**: `simulate_symbiosis(generations=5000)` runs the evolution loop, updating host, symbiont, and environment each generation.
- **Analysis**: Multiple simulation runs are collected, tracking:
  - Generations required for nitroplast development
  - Energy levels over time
- **Visualization**: Uses `matplotlib` to display:
  - Histogram of generations required for nitroplast development
  - Energy levels across generations for each simulation

5. Results and Evaluation

| Aspect                                 | Observation                                                |
|----------------------------------------|------------------------------------------------------------|
| Nitroplast Development Time             | Variable per simulation; tracked over 50 runs              |
| Energy Levels Over Generations          | Fluctuate depending on organelle efficiency and environment|
| Average Generations for Nitroplast      | Computed across simulations (e.g., ~X generations)        |
| Symbiont Survival                        | Dependent on energy production exceeding consumption       |

6. Interpretation of Results

- Simulations demonstrate stochastic nature of organelle evolution.
- Energy dynamics show trade-offs between organelle efficiency and survival.
- Faster nitroplast development occurs when environment favors high energy production.
- Results provide conceptual insights into symbiosis and organelle evolution, though abstracted.

7. Limitations

- The model is highly simplified and does not represent real biological processes.
- Energy calculations are heuristic and not chemically accurate.
- Mutation rates, thresholds, and efficiencies are arbitrary and parameterized for demonstration.
- No spatial or population-level interactions are modeled.
- Results are illustrative, not predictive of actual evolution.

