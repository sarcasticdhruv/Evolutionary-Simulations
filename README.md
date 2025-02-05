
# EvoSimExplorations

This repository contains two evolutionary simulation models that explore distinct aspects of evolution. The first model, contained in `new.ipynb`, simulates how organisms adapt in a 2D resource grid through mutation, crossover, and even horizontal gene transfer. The second model, in `evolution_pre-lim.ipynb`, demonstrates a transition from simple prokaryotic life to more complex eukaryotic forms by tracking genome complexity.

## How to Run
Open the notebooks in Jupyter Notebook or JupyterLab. Running the cells will simulate evolution and plot the average fitness over generations. Each notebook prints out its own summary results as well.

## Findings & Accuracy
- **new.ipynb**: Shows adaptive evolution in a resource-based grid with mechanisms like tournament selection and horizontal gene transfer. Estimated correctness ~80% (given its simplicity and intended educational use).
- **evolution_pre-lim.ipynb**: Illustrates the evolution from prokaryotic to eukaryotic life with a complexity threshold condition. Estimated correctness ~75% (with some arbitrary thresholds and a static environment).

Feel free to explore, experiment, and adapt these models for further study of evolutionary dynamics.


# general_evolution.ipynb - Ecological Evolution Simulation

## Overview
This notebook simulates the evolution of organisms in a 2D grid environment where resources are dynamically managed. Each organism has a genome, a self-adapting mutation rate, and a basic reproduction program involving crossover and mutation. Occasional horizontal gene transfer adds further diversity.

## How It Works
- **Resource Grid**: Organisms extract energy from a 50x50 grid whose resources decay and replenish over time.
- **Fitness**: Determined by energy consumption, with higher average fitness indicating better adaptation.
- **Reproduction**: Uses tournament selection for choosing parents, followed by crossover and mutation. Horizontal gene transfer occasionally occurs.
- **Phylogenetic Tracking**: A simple tree is built to track lineage diversification over 5000 generations.

## Results
The simulation shows steady improvements in fitness and diversity over time, reflecting adaptive evolution. It is a simplified model but effectively demonstrates key evolutionary processes.

# evolution_pre-lim.ipynb - Evolutionary Transition Simulation

## Overview
This notebook models the evolutionary transition from simple prokaryotic cells to more complex eukaryotic forms. It focuses on genetic crossover, mutation, and a condition-based evolution process that increases genome complexity.

## How It Works
- **Starting Point**: Organisms begin as prokaryotes with a simple genome.
- **Fitness Function**: Matches organism genome to a static environment, driving selection.
- **Reproduction**: Involves crossover and mutation. When a fitness criterion is met (e.g., average genome value > 0.75), the organism "evolves" to a eukaryotic state by expanding its genome.
- **Simulation**: Runs for 200 generations, tracking average fitness and the distribution between prokaryotic and eukaryotic cells.

## Results
The model demonstrates how increased genetic complexity can emerge under selective pressures, even though the threshold for evolution is arbitrarily set. It provides an educational demonstration of major evolutionary transitions.
