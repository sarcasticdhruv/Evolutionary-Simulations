**MODEL NAME**

Population-based Evolution Simulation (Prokaryotic to Eukaryotic Transition)

**1. Purpose of the Model**

This model simulates the evolution of a population of organisms over multiple
generations. Each organism has a genome represented as a numeric array, and
the simulation tracks fitness, reproduction, mutation, and the transition
from prokaryotic to eukaryotic cell types under evolutionary pressures.

**2. Key Concepts and Assumptions**

- Each organism starts as prokaryotic with a low-complexity genome.
- Evolution to eukaryotic occurs when average genome value exceeds a threshold (>0.75).
- Organisms reproduce via **crossover** and **mutation**, modeling sexual reproduction.
- Fitness is calculated as the dot product between the organism’s genome and the environment.
- The environment is randomly generated and affects evolution; it has double the genome length to accommodate both cell types.
- Only the top 50% of organisms by fitness reproduce each generation.
- The simulation abstracts biological realism and focuses on evolutionary concepts.

**3. Model Logic**

1. Initialize a population of prokaryotic organisms with simple genomes.
2. For each generation:
   - Calculate fitness scores for all organisms.
   - Select the fittest half for reproduction.
   - Generate offspring via crossover of two parents.
   - Apply random mutations to each offspring genome.
   - Attempt evolution to eukaryotic if genome average exceeds threshold.
   - Track average fitness across the population.
3. Continue for a fixed number of generations or until stopping condition is reached.
4. Record the number of prokaryotic and eukaryotic organisms at the end.

**4. Code Implementation**

- **Classes**:
  - `Organism`: Represents an individual with genome, cell type, mutation, crossover, and evolution logic.
- **Functions**:
  - `fitness_function(organism, environment)`: Calculates fitness as the sum of genome × environment.
  - `create_environment(genome_length)`: Generates a random environment vector.
  - `simulate_evolution(population_size, generations, mutation_rate)`: Runs the full evolutionary loop.
- **Visualization**:
  - Plots average fitness over generations using `matplotlib`.
- **Analysis**:
  - Counts the number of eukaryotic vs. prokaryotic organisms in the final population.

**5. Results and Evaluation**


| Aspect                    | Observation                                               |
|---------------------------|-----------------------------------------------------------|
| Average Fitness Over Time  | Increases as evolution favors fitter organisms          |
| Population Composition     | Final number of prokaryotic vs. eukaryotic organisms    |
| Evolution Threshold        | Eukaryotic transition occurs when genome mean > 0.75     |
| Fitness Improvement        | Tracks adaptation of population to environment          |

**6. Interpretation of Results**

- Fitness generally increases over generations as the fittest individuals reproduce.
- The eukaryotic transition demonstrates how complexity can emerge under selective pressure.
- Population diversity is maintained through crossover and mutation, preventing premature convergence.
- Results illustrate conceptual evolutionary dynamics, selection, and adaptation.

**7. Limitations**

- Genome and fitness are abstract numerical representations; not biologically accurate.
- Thresholds for evolution are arbitrary.
- Environment is static per generation except for random initial values.
- No spatial or ecological interactions; population is well-mixed.
- Only binary cell types (prokaryotic/eukaryotic) are modeled.

