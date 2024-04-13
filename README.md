# Multi-objective Evolutionary Algorithms for Influence Maximization in Hypergraph Networks
[\[Report\]](Report.pdf)

The goal of influence maximization (IM) is to reach the maximum number of entities in a network, starting from a small set of seed nodes, and assuming a model for information propagation. While this task has been widely studied in ordinary graph networks, IM in hypergraphs (where hyperedges represent interactions among more than two nodes) has not been adequately explored yet. This study introduces valuable algorithmic solutions to tackle the IM problem in hypergraph networks, including an original method based on hypergraph summarization suited for large-scale networks.

<p align="center">
<img src="https://github.com/StefanoGenettiUniTN/mo-ea-hypergraph-influence-maximization/assets/29599452/7ba61f67-bca3-43fd-b9a5-3f08e0f2f076" width="500">
</p>

## Requirements
Before getting started, make sure you have installed inspyred and hypergraphx.
```
pip install inspyred
pip install hypergraphx
```

## Structure
The repository is structured as follows:
```
    .
    ├── dataset                     # Hypergraphs dataset
    ├── ea                          # Files implementing the inspyred functions (evaluator, mutator, ...)
    ├── greedy                      # Implementation of the greedy baseline
    ├── random                      # Implementation of the random baseline
    ├── single-objective            # Implementation of the single objective optimization algorithm
    └── summarization               # Implementation of the summarization algorithm
```

## Usage
### Execute the algorithms
The following commands can be used to execute the algorithms:
- NSGA-II
    ```shell
    python main.py --hypergraph_path ".\dataset\amazon-antelmi\amazon.json"
        --max_generations 30
        --model IC
        --no_simulations 100
        --max_seed_nodes 0.01
        --output_file_path "output\moea.json"
        --output_execution_time_file_path
    ```
- GA (Single injective)
    ```shell
    python single-objective/single_objective.py
        --hypergraph_path ".\dataset\amazon-antelmi\amazon.json"
        --max_generations 30
        --model IC
        --no_simulations 100
        --max_seed_nodes 0.01
        --output_file_path "output\moea.json"
        --output_execution_time_file_path "output\moea.txt"
        --k_step 1 
        --probability 0.2
    ```
- High degree (Greedy)
    ```shell
    python greedy/high_degree.py
        --hypergraph_path ".\dataset\amazon-antelmi\amazon.json"
        --max_generations 30
        --model IC
        --no_simulations 100
        --max_seed_nodes 0.01
        --output_file_path "output\moea.json"
        --output_execution_time_file_path "output\moea.txt"
        --k_step 1
        --probability 0.2
    ```

- Random
    ```shell    
    python random/random_baseline.py
        --hypergraph_path ".\dataset\amazon-antelmi\amazon.json"
        --max_generations 30
        --model IC
        --no_simulations 100
        --max_seed_nodes 0.01
        --output_file_path "output\moea.json"
        --output_execution_time_file_path "output\moea.txt"
        --k_step 1
        --probability 0.2
    ```
### Plot the results
The Pareto front, the comparison between the algorithms and the network displaying the most influential nodes can be plotted using the methods in plot_utils.py. Some examples are written in the main method in the file.


## Contribution
Authors:
- Stefano Genetti, MSc Student University of Trento (Italy), stefano.genetti@studenti.unitn.it
- Eros Ribaga, MSc Student University of Trento (Italy), eros.ribaga@studenti.unitn.it
- Giovanni Iacca, Associate Professor University of Trento (Italy), giovanni.iacca@unitn.it

For every type of doubts/questions about the repository please do not hesitate to contact us.
