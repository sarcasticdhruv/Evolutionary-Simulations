# MODEL NAME
Spatial Grid-Based Evolution Simulation with Horizontal Gene Transfer

## 1. Purpose of the Model
This simulation models a population of organisms evolving in a 2D spatial environment. Each organism has a genome, mutation rate, and a reproduction program. The model tracks energy-based fitness, reproduction, mutation, horizontal gene transfer (HGT), and phylogenetic relationships over generations.

## 2. Key Concepts and Assumptions
- Organisms have numeric genomes representing traits and a reproduction program as a string.  
- Energy is obtained from the environment grid, and fitness is defined as energy consumed per generation.  
- Mutation is self-adaptive: organisms can mutate their genome and their mutation rate.  
- Reproduction occurs via crossover between two parents, with occasional mutations applied.  
- Horizontal Gene Transfer (HGT) allows a child to partially incorporate a neighbor’s genome with low probability.  
- Environment resources decay and replenish each generation.  
- Organisms occupy grid positions, which influence resource consumption.  
- Phylogenetic tracking is recorded using lineage IDs.  
- The simulation abstracts biological realism and focuses on conceptual evolutionary dynamics.

## 3. Model Logic
1. Initialize a population of organisms with random genomes and positions on a 2D grid.  
2. Initialize environment with uniform resource levels.  
3. For each generation:  
   - Update environmental resources (decay + replenishment).  
   - Calculate each organism’s energy intake based on genome traits and local resources.  
   - Record fitness scores and average population fitness.  
   - Select individuals for reproduction via tournament selection.  
   - Generate a new population through reproduction (crossover + mutation).  
   - Apply horizontal gene transfer with low probability.  
   - Place offspring near parent positions with grid wrap-around.  
   - Update phylogenetic tree tracking parent → children lineage IDs.  
4. Repeat for the specified number of generations.  
5. Record population, fitness history, and phylogenetic information for analysis.

## 4. Code Implementation
- **Classes**:  
  - `Organism`: Stores genome, mutation rate, reproduction program, lineage ID, and cell type; handles mutation, crossover, and reproduction.  
  - `Environment`: Maintains a 2D grid of resources; handles decay, replenishment, and consumption.  
- **Functions**:  
  - `tournament_selection(population, scores)`: Selects individuals based on fitness scores.  
  - `simulate_evolution(population_size, generations)`: Runs the full evolutionary simulation, tracking fitness and phylogeny.  
- **Simulation**: Tracks fitness over generations, population dynamics, and phylogenetic tree.  
- **Visualization**: Plots average fitness over generations using `matplotlib`.  
- **Analysis**: Prints phylogenetic tree summary (parent lineage → number of children).

## 5. Results and Evaluation
| Aspect                       | Observation                                                    |
|-------------------------------|----------------------------------------------------------------|
| Average Fitness Over Time      | Fitness generally increases as population adapts to environment |
| Population Dynamics            | Offspring inherit traits and mutation rates, maintaining diversity |
| Horizontal Gene Transfer       | Occasional genome sharing between neighbors introduces variation |
| Phylogenetic Tracking          | Lineage IDs allow mapping parent → offspring relationships     |

## 6. Interpretation of Results
- Average fitness typically increases over generations due to selection.  
- Self-adaptive mutation and HGT maintain population diversity.  
- Spatial structure of the environment introduces local competition for resources.  
- Phylogenetic tree enables tracking evolutionary relationships and lineage success.  
- Results illustrate conceptual evolutionary mechanisms, adaptation, and emergent complexity in a simplified ecosystem.

## 7. Limitations
- Genome, reproduction programs, and energy calculations are abstract representations and not biologically precise.  
- Mutation rates, HGT probability, and other parameters are arbitrarily chosen.  
- Environmental fluctuations are simplified; no explicit modeling of complex ecological interactions.  
- Population interactions are limited to local resource competition; no predation or multi-species interactions.  
- Results are illustrative, not predictive of real-world evolutionary outcomes.
